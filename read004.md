# Read: 04 - HTML Links, CSS Layout, JS Functions
## HTML
+ Links:
`<li><a href="http://www.empireonline.com">Empire</a></li>` Linking to Other Sites

`<li><a href="index.html">Home</a></li>` Linking to Other Pages on the Sa me Site

   * Relative Link Type:

`<a href="reviews.html">Reviews</a>`  Same Folder 

 `<a href="music/listings.html">Listings</a>` Child Folder
 
  `<a href="movies/dvd/reviews.html"> Reviews</a>` Grandchild Folder
  
 `<a href="../index.html">Home</a>` Parent Folder
 
 `<a href="../../index.html">Home</a>` GrandParent Folder
 
   * Email Links:
 
    mailto: `<a href="mailto:jon@example.org">Email Jon</a>`
    
   * Opening Links in a New Window:
 
     target: `<a href="http://www.imdb.com" target="_blank"> Internet Movie Database</a> (opens in new window)`
     
   * Linking to a Specific Part of Another Page  
     ```
     <h1 id="top">Film-Making Terms</h1>
     <a href="#arc_shot">Arc Shot</a><br />
     ```
  + Layout:
    * positioning schemes:
       1. Normal flow: each item to appear lower down the page `position:static`
       2. Relative Positioning: shifting it to the top, right, bottom, or left of where it `position:relative`
       3. Absolute positioning: ignore the space it would have taken up, top right, and the paragraphs start at the top of the screen `position:absolute`
       4. Fixed Positioning:stays in the exact same place. `position:fixed` 
       5. Floating Elements : `float: right;`
       6. `clear: left;`
       7. Overflapping elements: `z-index`

      
   ## Javascript
   Functions, Methods, and Objects” 
       * What is a FUNCTION : Functions let you group a series of statements together to perform a specific task.
       1. Declarinf function
       2. calling function
       3. getting a single value out of a function
       4. getting multible values out of a function
       *Example:
       
       ```
       function updateMessage() {
      var el = document.getElementByld('message'};
      el .textContent = msg;
        }
       updateMessage(};
         ```
 
   * What is an Object  : Objects group together a set of variables and functions to create a model of a something you would recognize from the real world. 
  
 ### 6 Reasons for Pair Programming:       
   pair programming is the practice of two developers sharing a single workstation to interactively tackle a coding task together.
 * How does pair programming work?
    While there are many different styles, pair programming commonly involves two roles: the Driver and the Navigator.
    1. The Driver is the programmer who is typing and the only one whose hands are on the keyboard.
    2. The Navigator might also utilize their computer as a second screen to look up solutions and documentation, but should not be writing any code.
 * Why pair program? 
        Pair programming touches on all four skills: developers explain out loud what the code should do, listen to others’ guidance, read code that others have written, and           write code themselves. 
    1. Greater efficiency
    2. Engaged collaboration 
    3. Learning from fellow students
    4. Social skills
    5. Job interview readiness
    6. Work environment readiness
      
 ### References
 From the Duckett HTML book:

Chapter 4: Ch.4 “Links” (pp.74-93)

Chapter 15: “Layout” (pp.358-404)


From the Duckett JS book:

Chapter 3 (first part): “Functions, Methods, and Objects” (pp.86-99 ONLY)

Article: [6 Reasons for Pair Programming](https://www.codefellows.org/blog/6-reasons-for-pair-programming/)