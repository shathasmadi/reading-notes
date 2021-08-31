# Read 29 : Room

***

## Save data in a local database using Room   

Apps that handle non-trivial amounts of structured data can benefit greatly from persisting that data locally. The most common use case is to cache relevant pieces of data so that when the device cannot access the network, the user can still browse that content while they are offline.
The Room persistence library provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite. In particular, Room provides the following benefits:

1. Compile-time verification of SQL queries.
2. Convenience annotations that minimize repetitive and error-prone boilerplate code.
3. Streamlined database migration paths.

***

## Define relationships between objects:

* Create embedded objects: Sometimes, you'd like to express an entity or data object as a cohesive whole in your database logic, even if the object contains several fields. In these situations, you can use the @Embedded annotation to represent an object that you'd like to decompose into its subfields within a table. You can then query the embedded fields just as you would for other individual columns.

***
### to use Room in your app:

* add the following dependencies to your app's build.gradle file:

```
dependencies {
    def room_version = "2.3.0"

    implementation "androidx.room:room-runtime:$room_version"
    annotationProcessor "androidx.room:room-compiler:$room_version"

    // optional - RxJava2 support for Room
    implementation "androidx.room:room-rxjava2:$room_version"

    // optional - RxJava3 support for Room
    implementation "androidx.room:room-rxjava3:$room_version"

    // optional - Guava support for Room, including Optional and ListenableFuture
    implementation "androidx.room:room-guava:$room_version"

    // optional - Test helpers
    testImplementation "androidx.room:room-testing:$room_version"

    // optional - Paging 3 Integration
    implementation "androidx.room:room-paging:2.4.0-alpha04"
}
```
***

## There are three major components in Room:
1. The database class that holds the database and serves as the main access point for the underlying connection to your app's persisted data.
2. Data entities that represent tables in your app's database.
3. Data access objects (DAOs) that provide methods that your app can use to query, update, insert, and delete data in the database.

![image](room_architecture.png)

***
 
## Defining data using Room entities

When you use the Room persistence library to store your app's data, you define entities to represent the objects that you want to store. Each entity corresponds to a table in the associated Room database, and each instance of an entity represents a row of data in the corresponding table.
That means you can use Room entities to define your database schema without writing any SQL code.

* Anatomy of an entity: You define each Room entity as a class that is annotated with ```@Entity```. A Room entity includes fields for each column in the corresponding table in the database, including one or more columns that comprise the primary key.

* Define a primary key: Each Room entity must define a primary key that uniquely identifies each row in the corresponding database table. The most straightforward way of doing this is to annotate a single column with ```@PrimaryKey```.

```
@PrimaryKey
public int id;
```

* Define a composite primary key: If you need instances of an entity to be uniquely identified by a combination of multiple columns, you can define a composite primary key by listing those columns in the primaryKeys property of ```@Entity```.

* Ignore fields: By default, Room creates a column for each field that's defined in the entity. If an entity has fields that you don't want to persist, you can annotate them using ```@Ignore```.

* Provide table search support: Room supports several types of annotations that make it easier for you to search for details in your database's tables. Use full-text search unless your app's minSdkVersion is less than 16.

***
## Usage
* After you have defined the data entity, the DAO, and the database object, you can use the following code to create an instance of the database:


```

AppDatabase db = Room.databaseBuilder(getApplicationContext(),
        AppDatabase.class, "database-name").build();

```
