---
title: "Day 27: Python Excel Work"
date: 2015-01-20
---

At work I've been doing a lot with Python when I can. 

I've been working with another analyst and some engineers to plan a Python course for analysts so that our department will knew how to read and write Python code. I think it's a very useful language for Data Analytics, and it will allow us to do a lot of things that many didn't think were possible.

I've also been working on a project of my own using `openpyxl`. There are a lot of cases where analysts need to output data to Excel, and sometimes it would just be easier to do it in Unix than to manually copy and paste everything into files and different tabs.

So, I've been writing a module that analysts could use that creates excel files and writes to them. I'm also currently working on writing two tools to output data. One will just take stdin and write to a sheet in a workbook that the user specifies. That's the easier one.

The one that I'm really excited about is the other tool, which will read stdin, and based on the label of some column specified by the user it will output corresponding records to the sheet with that label. As of right now the file needs to be sorted but later on I may make it so any file can be used. So for example, say there's a sorted tab delimited input file that looks like this:

	user1	label1	hereisdata	more
	user2	label1	datadata	hello
	user1	label2	blahblah	data
	user4	label2	moredata	evenmore
	
The user would cat or zcat that file, then pipe into the tool and specify the workbook name, the label colum (0-based) and what cell the data should start at (the default is A1). The output workbook would have two tabs:

label1

	user1	label1	hereisdata	more
	user2	label1	datadata	hello
	
label2

	user1	label2	blahblah	data
	user4	label2	moredata	evenmore
	
I'm hoping that when I roll this out to my team that people will find it useful. I think for cases where there are a bunch of metrics that need to be on different tabs this will be really helpful; I know I have a project where I'll definitely want to use this rather than split everything up by hand.