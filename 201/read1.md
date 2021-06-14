# **HTML Notes:**


## WHAT/WHY/HOW:
+ **WHAT**: HTML is HyperText Markup Language, it's the markup language used to create the structure of the web pages.

+ **WHY**: without HTML the browser won't understand your code and won't differentiate between different text types (headding, image, paragraph).

+ **HOW**: HTML elements consists of openning tag, closing tag, content and attributes.
  > example: `<p id='greeting'>hi</p>`.

  > where:  `<p>` is the openning tag.
  > `</p>` is the closing tag.
  > `id='greeting'` arttribute.
  > `hi` content.

## Example:
  ```HTML
  <!DOCTYPE html> this tag used to tell the browser that we use HTML5
  <html> this tag used to tell the browser that all the content inside is HTML
    <head> this tag used to put all the information about the page
      <title></title> this tag used to specify the page title.
    </head>
    <body> this tag used to put inside it everything that will dispaly in the page window.

    </body>
  </html>
  ```
## Definitions list:
+ HTML >> HyperText Markup Language.
+ CSS >> Cascading Style Sheets.
+ Browser >> Software for access the world wide web.
+ DNS >> Domain Name System.
+ Tag >> keywords used in HTML defines how web browser will format and display the content. Like (`<P>`)
+ Attribute >> special words used inside the opening tag to control the element's behaviour. Like (`<p id='p1'>`)
+ File extenstion >> is the suffix at the end of a filename that indicates what type of file it is. Like (.html)
+ Block Elements >> HTML elements which starts a new line. Like (`<h1>, <p>, <ul>`).
+ Inline Elements >> HTML elements which continue on the same line. Like (`<a>, <span>, <img>`).
+ Site maps >> diagram of the pages that will be used to structure your site. 
+ Wireframes >> is a sketch that shows how your web page will look like.

## Cheat sheet:
+ `<!DOCTYPE>` Defines the document type
+ `<html>` Defines an html document
+ `<head>` Defines information about the document
+ `<title>` Defines the document title
+ `<body>` Defines a body element
+ `<!-- -->` Defines a comment
+ `<h1> to <h6>` Defines header 1 to header 6 
+ `<p>` Defines a paragraph
+ `<a>` Defines a hyperlink
+ `<img>` Defines an image
+ `<ul>` Defines an unordered list
+ `<script>` Defines a javascript code
+ `<style>` Defines a CSS code

## Quiz:
 > *create a basic HTML web page structure that have a header (h1) and paragraph. give the header (id) attribute and give the paragraph (class) attribute.*


# **Javascript Notes:**


## WHAT/WHY/HOW:
+ **WHAT**: Javascript is a programming language that allows you to make the web pages interactive.

+ **WHY**: Javascript convert a web page from static to dynamic, and it contain loops, conditions, math, functions.

+ **HOW**: You can add Javascript to your code internally by using `<script>` tag inside the HTML page, or externlly by creating (.js) file and link it to the HTML page (`<script src="script.js"></script>`)

## Example:
```javascript
document.write('Hello, world')
```
+ `document` is the object, the object represent the entire web page.
+ `.` is the member operator, each object contain several methods and to access the member e use dot `.`.
+ `write()` is a method, this method allow me to write on the HTML page.
+ `'Hello, world'` is a parameter of the `write()` method.

## Definitions list:

+ Script >> is a sequence of instructions that executed step by step by the computer to achieve a goal.
+ Flowchart >> high level view of the a script tasks.
+ Objects >> Representation of a physical thing.
+ Propertites >> tell us about the object characteristics.
+ Methods >> perform tasks using the propertites of an object.
+ Events >> triggered when a user interacts with the page (click, hover..etc)

## Cheat sheet:

+ `var` Defines a variable
+ `document.write()` Write directly to the HTML document
+ `if (condition) { code }` If Statement
+ `prompt()` Creates an dialogue for user input
+ `console.log()` Writes information to the browser console, used for deevelopers.
+ `alert()` Output data in an alert box in the browser window
+ `//` single line comment
+ `/* */` Multi line comment
  
## Quiz:
> *Write A javascript code to add a (hello, world) text to the web page. create extenal javascript file and link it to your HTML page.*
