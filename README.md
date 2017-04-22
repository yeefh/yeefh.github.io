## Website Optimization Project

This Readme file include:

1. Details to successfully run the the application
2. Outlines optimizations made in index.html and views/js/main.js for pizza.html

### To Run index.html
Open the browser and visit http://yeefh.github.io.

#### Optimizing index.html for PageSpeed Insights score
1. Instead of linking stylsheets, all styles are embedded into index.html.
This remove the trip to the server to retrieve web fonts.

1. Reduced file sizes for images
* profilepic.jpg (15KB) reduced to to 2KB
* build_your_own.jpg (5KB) reduced to 3KB
* mobile_web.jpg (4KB) reduced to 3KB
* optimize.jpg (5KB) reduced to 4KB

### To Run pizza.html
Open the browser and visit http://yeefh.github.io/views/pizza.html.

#### Optimizing Computational Efficiency (Pizza size slider)
1. In **changePizzaSizes** function, variables *dx*, *newwidth* are static values which only need to calculated once. Took these out from the loop.

2. *windowWidth* var moved from **determineDx** function to **changePizzaSizes** funtion. Add new parameter *windowWidth* to **determineDx** function.

3. Made **resizePizzas** function more modular and easier to read by moving the following functions out:
    * **determineDx**
    * **changePizzaSizes**

4. Store the query selector document.querySelectorAll(".randomPizzaContainer") into a var outside the loop as the number of elements is static.


### Optimizing Frame Rate when Scrolling
1. Store document.body.scrollTop / 1250 into a var outside the loop as the value is static.

2. Store document.querySelector("#movingPizzas1") into a var outside the loop as the number of elements is static.
