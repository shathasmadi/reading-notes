# Read: 13 - Local Storage

## **Cookies:**

+ It is a store that saves your preferences on the Internet sites in terms of your preferences can be used for persistent local storage of small amounts of data, things that you prefer, and things that you pay attention to like: ``Clothes, Cars, Commodity, etc.``
 

+ She has more negatives than positives in her presence such as:

1- Cookies: are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over  and over

2- Cookies** are included with every HTTP request, thereby sending data unencrypted over the internet (unless your entire web application is served over SSL)

3- Cookies are limited to about 4 KB of data — enough to slow down your application


+ userData: is allows web pages to store up to 64 KB of data per domain, in a hierarchical XML-based structure.
 

+ Gears: an open-source browser plugin In 2007, Google launched aimed at providing additional capabilities in browsers
 

+ Gears provide: 

1- an API to an embedded SQL database based on SQLite. After obtaining permission from the user once

2- Gears can store unlimited amounts of data per domain in SQL database tables 
 
+ HTML5 Storage: it’s a way for web pages to store named key/value pairs locally, within the client web browser. Like cookies,
 

+ Some Type of HTML5 storage support we use:
Chrome: 4.0+     Opera: 10.5+     FIREFOX :3.5+    SAFARI: 4.0+      ANDROID: 2.0+ 

+ access HTML5 Storage through the localStorage object on the global window object. Before you can use it, you should detect whether the browser supports it.
 
+ Instead of writing this function yourself, you can use Modernizr to detect support for HTML5 Storage.
 
+ the data is actually stored as a string. If you are storing and retrieving anything other than strings, you will need to use functions like parseInt() or parseFloat() to coerce your retrieved data into the expected JavaScript datatype.
 
+ Calling setItem() with a named key that already exists will silently overwrite the previous value. Calling getItem() with a non-existent key will return null rather than throw an exception.
 
+  there is a property to get the total number of values in the storage area, and to iterate through all of the keys by index (to get the name of each key).
 
 
 # Recources:
 
 [THE PAST, PRESENT & FUTURE OF LOCAL STORAGE FOR WEB APPLICATIONS](http://diveinto.html5doctor.com/storage.html)
 
 
 [DETECTING HTML5 FEATURES](http://diveinto.html5doctor.com/detect.html#storage)
 
