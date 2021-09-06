# Read 33 : GraphQL @connection

### Add relationships between types
- **@connection** -> to specify relationships between @model types. 
1. This supports one-to-one, one-to-many, and many-to-one relationships. 
2. You may implement many-to-many relationships using two one-to-many connections and a joining @model type. 


- **Usage**
 **@model** -> to specify relationships between models. 

The keyName argument can optionally be used to specify the name of secondary index (an index that was set up using @key) that should be queried from the other type in the relationship.

- If keyName is not provided, then @connection queries the target table's primary index.

- **Has one** -> to define a one-to-one connection where a project has one team:

```
type Project @model {
  id: ID!
  name: String
  team: Team @connection
}

type Team @model {
  id: ID!
  name: String!
}
```

Also as like this:

```
type Project @model {
  id: ID!
  name: String
  teamID: ID!
  team: Team @connection(fields: ["teamID"])
}

type Team @model {
  id: ID!
  name: String!
}
```


After it's transformed, you can create projects and query the connected team as follows:

```
mutation CreateProject {
  createProject(input: { name: "New Project", teamID: "a-team-id"}) {
    id
    name
    team {
      id
      name
    }
  }
}
```


- **Has many**


```
type Post @model {
  id: ID!
  title: String!
  comments: [Comment] @connection(keyName: "byPost", fields: ["id"])
}

type Comment @model
  @key(name: "byPost", fields: ["postID", "content"]) {
  id: ID!
  postID: ID!
  content: String!
}
```

- **Belongs to**

You can make a connection bi-directional by adding a many-to-one connection to types that already have a one-to-many connection. 


```
type Post @model {
  id: ID!
  title: String!
  comments: [Comment] @connection(keyName: "byPost", fields: ["id"])
}

type Comment @model
  @key(name: "byPost", fields: ["postID", "content"]) {
  id: ID!
  postID: ID!
  content: String!
  post: Post @connection(fields: ["postID"])
}
```

- **Many-to-many connections**

You can implement many to many using two 1-M @connections, an @key, and a joining @model. For example:

  
```
type Post @model {
  id: ID!
  title: String!
  editors: [PostEditor] @connection(keyName: "byPost", fields: ["id"])
}

# Create a join model and disable queries as you don't need them
# and can query through Post.editors and User.posts
type PostEditor
  @model(queries: null)
  @key(name: "byPost", fields: ["postID", "editorID"])
  @key(name: "byEditor", fields: ["editorID", "postID"]) {
  id: ID!
  postID: ID!
  editorID: ID!
  post: Post! @connection(fields: ["postID"])
  editor: User! @connection(fields: ["editorID"])
}

type User @model {
  id: ID!
  username: String!
  posts: [PostEditor] @connection(keyName: "byEditor", fields: ["id"])
}
```