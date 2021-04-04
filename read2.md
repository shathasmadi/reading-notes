
html

Definitions list:
Structural markup: the elements that you can use to 
describe both headings and paragraphs

Semantic markup: which provides extra information; such 
as where emphasis is placed in a sentence

Headings to provide a heading for the web sit

Cheat sheet:


p To create a paragraph

<b> text bold
<i> text Italic
<br />  line break
<hr /> horizontal line
<strong> to indicates that its 
content has strong importance.

<blockquote> is used for longer quotes that take 
up an entire paragraph.

<cite> element can be used 
to indicate where the citation is 
from.

The <dfn> element is used to 
indicate the defining instance of 
a new term

<address>  to contain 
contact details for the author of 
the page

<ins>
<del>
Changes to Content


CSS 
what is css Cascading Style Sheets

why css?
 CSS allows you to create rules that specify how the content of 
an element should appear

how css 
CSS works by associating rules with HTML elements. These rules govern 
how the content of specified elements should be displayed.
example

body {
 font-family: arial;
 background-color: rgb(185,179,175);}
h1 {
 color: rgb(255,255,255);}

three way to apply css in the page 
1- Inline : <p style="color= red"> </p>
2-Internal: <style type="text/css"> </style>
3-External: <link href="css/styles.css" type="text/css"> 

CSS rules usually appear in a separate document, 
although they may appear within an HTML page.

css Selectors
Type Selector...> h1, h2, h3 {}
class selector ...> .not{}
id selector ...> # note{
}

qiuz 
1-write three kind of selectors in css?
2- write three element of html

javascript

WHAT:Javascript is a programming language that allows you to make the web pages interactive.

WHY:Javascript convert a web page to be dynamic.

HOW: we can use javascript in our code either internal<script> </script> or external <script src="script.js"></script>
 example
var today= new Date{); 
var hourNow = today.getHours{) ;

Definitions list:
A script..> is a series of instructions that a computer can follow one-by-one. 
Each individual instruction or step is known as a statement.


{}...> curly braces

JAVASCRIPT IS CASE SENSITIVE...> that mean if you write A and a they are different.

comments...>o explain what your code does. 
They help make your code easier to read and understand. 

variables...> to store a value

An array...> is a special type of variable. It doesn't 
just store one value; it stores a list of values.

An expression evaluates into (results in) a single value. Broadly speaking 
there are two types of expressions. 
1-ASSIGN A VALUE TO A VARIABLE
2- USE TWO OR MORE VALUES TO RETURN A SINGLE VALUE 


Cheat sheet:
var x ...< declare a variable
x = ...> assign a value.

Data type
(1, 1.2) number
true or false boolean
"abcd" string

var colors; 
colors ['white', 'black', ' custom'];...> declare array.

Each item in an array is 
automatically given a number 
called an index.

var itemThree; 
itemThree = col ors [2] ;...> to access the third number in array.

var numColors ; 
numColors =col ors. length;...> to know number of items in the an array

 

Expressions + Operators

expression 1-EXPRESSIONS that just assign a value to a variable such as (var color = ‘beige’; ) 2- EXPRESSIONS THAT USE TWO OR MORE VALUES TO RETURN A SINGLE-VALUE such as (var area = 3 * 2; )

ARITHMETI C OPERATORS such as (+ ,- , *, /,++,–,%).

STRING OPERATOR like + symbol that connects two string together

 