# Read: 07 - HTML Tables; JS Constructor Functions
## Domain Modeling

> Domain modeling is the process of creating a conceptual model in code for a specific problem. A model describes the various entities, their attributes and behaviors, 
  as well as the constraints that govern the problem domain. An entity that stores data in properties and encapsulates behaviors in methods is commonly referred to as 
  an object-oriented model.

## Functions, Methods, and Objects
 > + creating an object constructor notation:`var objectName= new object()`
 > + creat many oject constructor notations :`function Hotel (name, rooms, booked) {`
```
function Hotel (name, rooms, booked) {
this .name = name;
this.rooms = rooms;
this.booked = booked;
this.checkAvailability = function()
return this.rooms - this.booked;
} ;
```
> + CREATE THE OBJECT:
  >  + literal notation:            
 ```
var hotel = {}                            
hotel .name= 'Quay';
hotel .rooms = 40;
hotel.booked = 25;
hotel.checkAvailabil ity =function()
return this . rooms - this .booked;{
} ;
```


> + OBJECT CONSTRUCTOR NOTATION:
   
  
 ```
  var hotel = new Object();
  hotel.name = 'Quay';
  hotel .rooms = 40 ;
  hotel . booked= 25;
  hotel.checkAvailability =function()
   return this .rooms - this .booked;{
   } ;
   
   ```
 
 + PROPERTIES

  1. `length` : Returns number of characters in the string in most cases (see note bottom-left)
  2. `toUpperCase ()` Changes string to uppercase characters
   `tolowerCase ()` Changes string to lowercase characters
  3. `charAt ()` Takes an index number as a parameter, and returns set of characters is found within the string
  4. `indexOf()` Returns index number of the last time a character or set of characters is found within the string
  5. `lastlndexOf()` :Returns index number of the last time a character or set of characters is found within the string
  6. `substring()` :Returns characters found between two index numbers where the character for the first index number is included and the character for the last index number is           not included
  7. `split()` :When a character is specified, it splits the string each time it is found, then stores each individual part ih an array
  8. `trim()` : Removes whitespace from start and end of string
  9. `replace() ` :Like find and replace, it takes one value that should be found, and another to replace it (by default, it only replaces the first match it finds)


  + METHODS:
    1. `getDate() setDate()` :Returns I sets the day of the month (1-31)

    2. `getDay ()`:Returns the day of the week (0-6)
    3. `getFul1 Year() setFul1 Year ()` :Returns I sets the year (4 digits)
    4. `getHours () setHours ()`: Returns I sets the hour (0-23)
    5. `getMi11i seconds () setMi11i seconds () `:Returns I sets the milliseconds (0-999)
    6. `getMi nutes () setMi nutes ()`: Returns I sets the minutes (0-59)
    7. `getMonth () setMonth ()`:  Returns/ sets the month (0-11)
    8. `getSeconds() setSeconds()` Returns I sets the seconds (0-59) 
    9. `getTime() setTime() ` : Number of milliseconds since January 1, 1970, 00:00:00 UTC (Coordinated Universal Time)
   10. `getTimezoneOffset ()` : Returns time zone offset in mins for locale
   11. `toDateString ()` : Returns "date" as a human-readable string
   12. `to TimeString ()`: Returns "time" as a human-readable string
   13. `to String()` : Returns a string representing the specified date

## Tables

> + **What's a table ?**
   A table represents information in a grid format. Examples of tables include financial reports, TV schedules, and sports results.
> +  **How to create tables?**
     > `<table>` : element is used to create a table.
     > `<tr>`:(The tr stands for table row.)
     >  `<td>`:(The td stands for table data.)
     >  `<th> `: table heading

## Resources 
> [Domain Modeling](https://github.com/codefellows/domain_modeling#domain-modeling)

> From the Duckett JS Book:Chapter 3: “Functions, Methods, and Objects” (pp.106-144)

> From the Duckett HTML book:Chapter 6: “Tables” (pp.126-145)
