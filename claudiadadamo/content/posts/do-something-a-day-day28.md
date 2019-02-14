---
title: "Day 28: The Stable Marriage Problem"
date: 2015-02-09
---


Today I read an [article](http://fivethirtyeight.com/features/another-34000-people-are-about-to-put-their-future-in-the-hands-of-an-algorithm/) about the residency match process for med school graduates and how placement is decided by an algorithm. 

I decided to look more into it. The problem is called the [Stable Marriage Problem](http://en.wikipedia.org/wiki/Stable_marriage_problem), and describes a situation where two groups of people (in the med school case schools and applicants; in this case men and women) rate their partners in order of preference, and marriages aren't "stable" until each man or woman is paired with the best partner possible. The algorithm to solve the problem was presented by David Gale and Lloyd Shapley in 1962, and they determined that it is always possible to solve the problem and achieve stable relationships for everyone.

The algorithm in pseudocode would be something like this:

<pre><code>
while there is at least one man (for \
this example, Phil) who is unmatched:
	Phil proposes to the highest ranked	woman \
	that he has not proposed to yet (Marie)
	if Marie is not engaged:
		Marie and Phil become engaged
	if Marie is engaged:
		if Marie prefers Phil to her current fiance:
			Marie becomes engaged to Phil \
			and her current fiance is now unmatched
		else:
			Phil is still unmatched</code></pre>

I love reading about algorithms like these and how they're applied in real life. At the bottom of the Wikipedia article they mention other similar problems, like how to find the "stable marriages" of med students and residence programs when the residence programs can accept more than one "proposal", or how to do so with med students wishing to be in the same residency program as their significant others.

Here's a great visualization of the algorithm: 
<iframe width="560" height="315" src="https://www.youtube.com/embed/Qcv1IqHWAzg" frameborder="0" allowfullscreen></iframe>	

Sources:

Wikipedia - http://en.wikipedia.org/wiki/Stable\_marriage\_problem
