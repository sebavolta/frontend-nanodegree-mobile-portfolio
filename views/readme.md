#Rendering Optimization

To run the application, open the pizza.html in Chrome browser.

#Optimizations made:
- In pizza.html I removed the inline width for the images container and added 
the class 'pizza-resize' to the images.
- In css/style.css I updated the following rules in '.randomPizzaContainer':
	- Added width and height.
	- Removed display rule.
- in js/main.js I removed the inline width of the pizza images container
and added the class 'pizza-resize' to each image.
- I compressed the pizza.png image.

#Resize optimizations:
- I added a global 'pizzaResizeItems' var to store all the pizzas items and 
be available in resizing functions.
- I generated the function 'animationSize' that calls the 'requestAnimationFrame'
before calling the 'changePizzaSizes', to be sure the change will apply during
the refreshing of the browser.
- I created a global var named 'size' so it is available under 'changePizzaSizes'
when it is called from 'requestAnimationFrame'.
- The 'changePizzaSizes' function iterates throug each image with the class
'pizza-resize', then calls the 'sizeSwitcher' function that returns the scale
depending on the slider, and finally it applies a 'Transform' to scale all
the images.

#Scrolling optimizations:
- I addied a global 'items' var to save the .mover items and be available 
in scolling functions
- I reduced the amount of elements because a lot of them are out of the screen.
- I removed the basic styles from the  '.mover' elements and set them into
the class on the css file.
- I changed the .mover element to a div, and applied a background image.
- The 'movingPizzas1' and 'pizzaGenerator' has now a 'translate3d' Z position
so they are positioned in diferent layers.
- All the .mover elements have a tranlate3d position when they are generated.
- The function 'updatePositionsRequest' is triggered when the user scrolls, and 
it calls the requestAnimationFrame sending the updatePosition as parameter,
so the code runs at the same time as the screen refreshes.
- Finally in the updatePosition function I moved the 'scrollTop' result to the 
'top' var so it is not called inside the iteration. Then the function iterates
through each .mover element and updates the 'translate3d' X and Z position without 
using 'left' position, so it affects the 'composite'.
