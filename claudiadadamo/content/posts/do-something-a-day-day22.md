---
title: "Day 22: Working through Django"
date: 2014-11-02
---

It's been confusing working through Django and sifting through the tutorials, but I think that I'm starting to get the hang of it!

Today I've been working on getting my Hangman app up and running. My friend Jake taught me more about how to set up apps in Django and gave me some pointers, so I was able to actually get something functional up and running.

Right now my app has a database which holds each game. A game consists of the word, the current state, a string of all letters guessed, and a count of how many wrong words they have guessed, plus some other variables. I've only stored one word, "hippopotamus", which I've been using as a tester. It's so satisfying seeing it work on the web!

This experience is awesome, because I get to work with all parts of the web app - the backend and the design. And I love that I can write Python code for it! For example, I store the word "hippopotamus" and the current state, which starts off as a string of underscores, one for each character in the word. I then take in the guess of the user, check to see if that word is in the string, and do the proper logic. I haven't tried using the `re` module in Python yet, but it worked well for finding instances of the character in my string. Here's an example of what I did:

	import re
	
	char_list = list(current_game.current_state)
	for m in re.finditer(new_guess, current_game.word):
		x = m.start()
		char_list[x] = new_guess

This splits the current state into a list, then finds all instances of the guessed letter in the string, and replaces the character in the 'current state' string at that index with the letter that the user has guessed.

My code is up on github at [https://github.com/claudiadadamo/hangman](https://github.com/claudiadadamo/hangman).