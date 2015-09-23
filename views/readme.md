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

#Resize optimizations:
- I generated the function 'animationSize' that calls the 'requestAnimationFrame'
before calling the 'changePizzaSizes', to be sure the change will apply during
the refreshing of the browser.
- I created a global var named 'size' so it is available under 'changePizzaSizes'
when it is called from 'requestAnimationFrame'.
- The 'changePizzaSizes' function iterates throug each image with the class
'pizza-resize', then calls the 'sizeSwitcher' function that returns the scale
depending on the slider, and finally it applies a 'Transform' to scale all
the images.