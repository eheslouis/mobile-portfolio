## Website Performance Optimization portfolio project

### How to run the application

After copying all the files, open index.html. This is the main page.
To view the different pages, just click on the few links.
For the "Cam's Pizzeria", you can scroll through the page and also change the size of the pizza via the scroll bar.

### My optimizations

* After running PageSpeed using Chrome, I followed the suggestions and resized the pizzeria image. Then I look at the code and identified necessary modifications: 
	* I moved the google fronts api to the bottom of the body.
	* I extracted the important CSS property using [Critical Path CSS Generator](https://jonassebastianohlsson.com/criticalpathcssgenerator/).
	* I moved the non critical CSS call to the bottom of the body. 
	* I added a media for the print.css call and also moved it to the bottom of the body.

This changes gave a score for mobile and desktop of 92 using PageSpeed.

* Then I worked on the frame rate:
	* I changed "querySelectorAll" to "getElementsByClassName" as this call is faster
	* I changed "querySelector" to "getElementById" as this call is faster
	* I declared the pizzasDiv variable outside of its loop to only make one call to the DOM. I did same for the movingPizzas.
	* I modified the updatePosition as well as the number of "mover" pizza

These changes allowed me to get to the 60fps.
* Finaly, I modified the changePizzaSizes to optain a resize time of about 1.2ms,
