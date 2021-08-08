# Read: 12 - Spring RESTful Routing & Static Files

### Spring Request Mapping

* `@RequestMapping(value = "/ex/foos", method = RequestMethod.GET)` I use it to connect request with methods, then I can extract request 
information using the @RequestMapping variables.

*  **@RequestMapping and the HTTP Method**: http has no default val, or it map to any request.

*  **RequestMapping and HTTP Headers** `@RequestMapping(value = "/ex/foos", headers = "key=val", method = POST`.

*  **RequestMapping With Path Variables**

* **@PathVariable annotation** use it make part of my url variable.

* example : `@RequestMapping(value = "/ex/foos/{whatever}/bar/", method = GET)`  {id} is  path var.

  * my method: `public String pathVariable( @PathVariable("whatever") int whatever)`.

* **RequestMapping & Request Parameters** : 

  * `@RequestMapping(value = "/ex/bars", params = "id", method = GET)`

  * `public String reqParam( @RequestParam("id") int id)`

* **Mapping Shortcuts**: `@GetMapping @PostMapping @PutMapping @DeleteMapping @PatchMapping`

  * Restful API and req map example:
  
```java
@GetMapping("/{id}")
public ResponseEntity<?> getBazz(@PathVariable String id){
    return new ResponseEntity<>(new Bazz(id, "Bazz"+id), HttpStatus.OK);
}

@PostMapping
public ResponseEntity<?> newBazz(@RequestParam("name") String name){
    return new ResponseEntity<>(new Bazz("5", name), HttpStatus.OK);
}

@PutMapping("/{id}")
public ResponseEntity<?> updateBazz(
  @PathVariable String id,
  @RequestParam("name") String name) {
    return new ResponseEntity<>(new Bazz(id, name), HttpStatus.OK);
}

@DeleteMapping("/{id}")
public ResponseEntity<?> deleteBazz(@PathVariable String id){
    return new ResponseEntity<>(new Bazz(id), HttpStatus.OK);
}
```

### Accessing Data with JPA

* Spring Data JPA to store and retrieve data in a relational database.

* required Dependencies in srping initializer **Spring Data JPA** and then** H2 Database**.

* `@Entity` annotation define entity.

* `@Id` using this will spring recognize each entity id.

* **Simple Queries**:

  * 
### Comparing repositories

* CrudRepository provides CRUD functions.

* PagingAndSortingRepository provides methods to do pagination and sort records.

* JpaRepository provides JPA methods such as delete records.

* because of inheritance relationship, the JpaRepository contains the full API of CrudRepository and PagingAndSortingRepositorym.

* it means When I don't full functionality repo usage, i can go with CrudRepository.

##### CrudRepository

Crud methods : 

`save() `

  * save an list of entities. 

  * we can pass multiple objects to save them in a batch

`findOne()` get a single entity by passing primary key value

`findAll()` – get an list of all available entities in database

`count()` – return the count of total entities in a table

`delete()` – delete an entity based on the passed object

`exists()` – verify if an entity exists based on the passed primary key value.

##### PagingAndSortingRepository

interface provides a method **findAll(Pageable pageable)**, it help me implement Pagination.

pageable object contain at least these 3 props: Page size, Current page number, Sorting.

* `Sort sort = new Sort(new Sort.Order(Direction.ASC, "lastName"));`

`Pageable pageable = new PageRequest(0, 5, sort);`

this code means, sort ascendant by last name and get me only 5 records.


#### JpaRepository

the interface props 

`findAll()`

get a List of all available entities in database

`findAll()`

 get a List of all available entities and sort them using the provided condition

`save() `

 save an list of entities. Here, we can pass multiple objects to save them in a batch

`flush()`

 flush all pending task to the database

`saveAndFlush() `

 save the entity and flush changes immediately

`deleteInBatch()` 

 delete an Iterable of entities. Here, we can pass multiple objects to delete them in a batch