---
title: "Day 1: Leap and Mutt"
date: 2014-09-19
tags: Do Something Every Day
---

Maybe having day one on a Friday wasn't the best idea since I have had only a few hours to work on something, BUT I feel really good and excited to even just work on the small things I've done tonight.

I started off aiming to set up my Leap Motion and work through a tutorial. I set it up and moved through the tutorial, and messed around with it enough to get something working that determines if the hand that's being put into the field is a right hand or left hand. A small achievement, but I haven't worked with the Leap Motion yet and it's exciting to see live data in the terminal when you run your code. I'm using Python, but there are a bunch of languages you can use with it. I've saved my code at [https://github.com/claudiadadamo/leapmotion/blob/master/leap-tester.py](https://github.com/claudiadadamo/leapmotion/blob/master/leap-tester.py).

<img src="http://www.claudiadadamo.com/photos/deuces_leap.jpg" width=300px >

After I got that working, I started thinking about this project and if there was any reason why people would want my new blog posts emailed to them. At work we use mutt, which is a text based program in Unix that allows you to read and send email. My personal laptop didn't have it installed, so I installed it and then I *attempted* to get it working. I wrote a script to write the body of my email to a file and mutt it, but I think I need to configure mutt to use my gmail account to be able to send emails from it. I found some resources online with directions of how to update the ~/.muttrc file to link it to Gmail, but I won't have enough time to work on it tonight.

I want to look into this more, because I think it would be really cool to automate sending emails with my blog posts. Ideally I would like to set up a crontab to check every night if there is a new post, and then email it. 