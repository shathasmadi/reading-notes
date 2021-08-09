# Related Resources and Integration Testing

## One-to-One Relationship

1. **The Data Model** : If we defind to two class with entity that mean we have one-to-one relationship and using @OneToOne annotation, if we wnt to customize the endpoint. we have to use @RestResource annotation.

for example :

```java
@OneToOne
    @JoinColumn(name = "address_id")
    @RestResource(path = "libraryAddress", rel="address")
    private Address address;
```

2. **The Repositories**: to create Repository we need to add interface fo this repository and extending the CrudRepository interface.

## One-to-Many Relationship

1. **The Data Model** : just we need to use @ManyToOnein the class and add the relationship to the other class who have relation with as well

for example:

```java
@ManyToOne
    @JoinColumn(name="library_id")
    private Library library;
```

```java
@OneToMany(mappedBy = "library")
    private List<Book> books;
```

2. **The Repositories**: to create Repository we need to add interface fo this repository and extending the CrudRepository interface

## Many-to-Many Relationship

1. **data model** : A many-to-many relationship is extablished with `@ManyToMany` annotation.

for example : 

```java
@ManyToMany(cascade = CascadeType.ALL)
    @JoinTable(name = "book_author", 
      joinColumns = @JoinColumn(name = "book_id", referencedColumnName = "id"), 
      inverseJoinColumns = @JoinColumn(name = "author_id", 
      referencedColumnName = "id"))
    private List<Book> books;
```

here the relation between authors and books a book can have many authors and vice versa.

2. **The Repositories**: to create Repository we need to add interface fo this repository and extending the CrudRepository interface