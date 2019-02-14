---
title: Exporting Wordpress posts for compatibility with Dropplets blogging platform
date: 2013-12-29
---

I recently found [Dropplets](http://dropplets.com/), which is a neat blogging platform that allows you to simply copy and paste files onto any server. Using Dropplets allowed me to host my blog on my own domain as opposed to hosting it on Wordpress. It has a clean file structure that makes it easy to customize and update on your own server. All I have to do is add Markdown files to the posts directory that is created for you, and they’re up on the page as long as they’re published. 

So, learning about Dropplets I set off to switch over my previous posts and try it out for a while. I learned that you can export Wordpress posts as an XML file, and after some googling I found out that someone made an XML to Markdown converter called [Exitwp](https://github.com/thomasf/exitwp). It’s for Jekyll, which is a static site generator. Exitwp allowed me to put my Wordpress exported XML file into a directory and create markdown files for each post that I had written. Jekyll has a similar markdown page structure to Dropplets, but after converting I realized that there were some things that were necessary to be placed in different orders at the top of each file. 

**** 
Jekyll markdown file header format: 

	author: claudiadadamo  
	comments: true  
	date: 2012-08-24 02:22:11+00:00  
	layout: post  
	slug: explosive-type-book-cover  
	title: Explosive Type Book Cover  
	wordpress_id: 59  
	categories:  
		- Graphic Design  
	post_format:  
		- Gallery       

****

Dropplets markdown file header format:

  
	#  Explosive Type Book Cover
	- Claudia D'Adamo
	- claudadamo
	- 2012/08/24
	- Graphic Design, Gallery
	- published   

****


I didn’t want to have to go by hand through all of the files changing around text, so I created a Python script that would rearrange the files that allowed me to upload them to the server without any further individual editing.

Check out my code at [https://gist.github.com/claudiadadamo/8170459](https://gist.github.com/claudiadadamo/8170459)

Here are the steps I went through:   
- Exporting my wordpress posts ( Dashboard > Tools > Export ), which creates an XML file that you download  
- Putting my XML file the directory specified by Exitwp and running that  
- Creating and running formatting script for Dropplets  
- Uploading all output files to the server


Interested in doing something similar or learning more? Let me know!