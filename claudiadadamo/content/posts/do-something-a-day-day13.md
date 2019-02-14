---
title: "Day 13: Python at Work"
date: 2014-10-01
---

Yesterday and today at work have been exciting because I've been working on a project that is really interesting! We needed to find all combinations of a list of 62 terms and do some formatting to be able to create output files that we could use in our scripts later on.

I've never worked with itertools before, but it was really easy and useful for the combinations part of the python script I wrote to be able to create these files. All you have to do is import itertools and you should be set to use .combinations(), .permutations(), etc. The one problem I had with this right off the bat is that python 2.5 doesn't have that functionality, and the shell at my office is set at python 2.5. Make sure that you run your script with python 2.7 (2.6 may support this, I'm not sure…) if you have more versions than just that.  
	
	python2.7 myscript.py

We worked through what the total number of combinations would be of length 2-5 with 62 items. If I were to create a loop to calculate it:
	
	sum=0
	for i in range(2,6):
		sum+=(math.factorial(62)/math.factorial(62-i))/math.factorial(i)
	print sum  

	
``*`` heads up - after this point I'm working from memory so there totally could be errors since I'm not looking at the script - I may be able to post it another time.  

So, this would output 7,068,558, which is the total number of combinations we needed to create. To do what I needed, I read in a two column, tab delimited file and saved each column to a list. Then, for each list I used `itertools.combinations(list,num)` where num is the number of items to use for the combinations (ranging from 2-6 in this case).   

After creating the objects, I looped through them using `zip` to join them together for each line for the new file. We wanted the first column to be regexes, so I joined the items in the first tuple by a regex string (ex. `".*".join(tuple1)`), and joined the second tuple by underscores (`"_".join(tuple2)`). In total the whole part of the script looked somethng like:  

	for n,r in zip(list1,list2):
		out_line=".*".join(n)+"\t"+"_".join(r)+"\n"  

		
zip is a cool function in python - it will return tuples at the same location in two sequences. If one sequence is smaller, it will only go until the end of the smaller one. By looping through the tuples in what zip returns I can get to each pairing and output them to the same row.  

I'm super excited about this project - I really liked using itertools and zip for this, and I learned a lot about more tools I can use in Python.