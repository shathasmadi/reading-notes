# Read: 12 - Docs for the HTML <canvas> Element & Chart.js
 + Creating a Chart
   to get started with Chart.js. All that's required is the script included in your page along with a single `<canvas>` node to render the chart.
 + after cloning the Chart.js repo to a local directory, and navigating to that directory in the command line, 
  we can run the following: `> npm install` This will install the local development dependencies for Chart.js.
 + First, we need to have a canvas in our page. `<canvas id="myChart"></canvas>`
 + we need to include Chart.js in our page. `<script src="https://cdn.jsdelivr.net/npm/chart.js@2.8.0"></script>`
 + Now, we can create a chart. We add a script to our page:
  
```
var ctx = document.getElementById('myChart').getContext('2d');
var chart = new Chart(ctx, {
    // The type of chart we want to create
    type: 'line',

    // The data for our dataset
    data: {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
        datasets: [{
            label: 'My First dataset',
            backgroundColor: 'rgb(255, 99, 132)',
            borderColor: 'rgb(255, 99, 132)',
            data: [0, 10, 5, 2, 20, 30, 45]
        }]
    },

    // Configuration options go here
    options: {}
}); 
```
 
 + Chart.js can be installed **via npm or bower**. It is recommended to get Chart.js this way. `npm install chart.js` `--save bower install chart.js --save`
 +  canvas
     +  At first sight a `<canvas>` looks like the `<img>` element, with the only clear difference being that it doesn't have the src and alt attributes. 
     + the `<canvas>` element has only two attributes, width and height
     +  `<canvas>` only supports two primitive shapes: rectangles and paths (lists of points connected by lines).
          + `fillRect(x, y, width, height)` :Draws a filled rectangle.
          + `strokeRect(x, y, width, height)` :Draws a rectangular outline.
          + `clearRect(x, y, width, height)` :Clears the specified rectangular area, making it fully transparent.
          + example:
          ```
        function draw() {
        var canvas = document.getElementById('canvas');
        if (canvas.getContext) {
         var ctx = canvas.getContext('2d'); 
        ctx.fillRect(25, 25, 100, 100);
         ctx.clearRect(45, 45, 60, 60);
         ctx.strokeRect(50, 50, 50, 50);
          }
         }
        ```
        + `fillRect()` :function draws a large black square 100 pixels on each side.
        + `clearRect()`: function then erases a 60x60 pixel square from the center
        + `strokeRect()`: is called to create a rectangular outline 50x50 pixels within the cleared square.
        
+ The first step to create a path is to call the `beginPath()`
+ beginPath():Creates a new path. 
+ Path methods:Methods to set different paths for objects
+ closePath():Adds a straight line to the path, going to the start of the current sub-path.
+ stroke():Draws the shape by stroking its outline.
+ fill():Draws a solid shape by filling the path's content area.
 #### Applying styles and colors
 + Colors:
   +` fillStyle = color`:Sets the style used when filling shapes.
   + `strokeStyle = color`:Sets the style for shapes' outlines.
  
  #### REFERENCES
  [Chart.js](https://www.chartjs.org/docs/2.9.4/general/options.html)
  
  [basic usage of canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage)
  
  [Drawing shapes with canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes)
  
  [Applying styles and colors](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors)
  
  [Drawing text](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text)
  
  
  
 
 


