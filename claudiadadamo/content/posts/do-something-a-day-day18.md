---
title: "Day 18: Playing With Processing"
date: 2014-10-14
---

Tonight I played around a bit with Processing, which is a programming language used mostly for electronic arts and design. 

I started off trying to create a Star class that would sparkle. Eventually I got something working:

My `Star` class is initiated with randomized x and y locations, diameter and how much shine (how much larger the diameter will get). 
	c = color(255,255,0);
	diam = random(150);
	loc_x = random(250)+diam; 
	loc_y = random(250)+diam; 
	how_much_shine = random(7);
	
My draw function in the main part of the program displays the objects, and then every 2 seconds will call `sparkle()` on the stars.

The `sparkle()` function is very simple, it just changes the diameter of the star to be `diam = diam+how_much_shine*random(-5,5)`. It randomly selects a float between -5 and 5, and multiplies it by how much shine to get a random sparkle amount. I decided to do it this way so that every time the amount of shine changes, but it's all related back to how much shine there is for the star. Stars with more shine will have more with larger numbers (ex. 5), but they're also able to lose shine just as easily (ex. with -5).

Next steps for this particular project would be to try to dynamically create stars based on some situation (for example, it would create a new star if a star becomes larger than 2x its diameter.) I'd also like to add checks in to make sure that stars don't ever fully disappear or overlap with eachother.

You can check out what I made here: [http://www.openprocessing.org/sketch/166259](http://www.openprocessing.org/sketch/166259). You can also take a look at my code there too. If you don't see three stars right away, just refresh the page.