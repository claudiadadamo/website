---
title: "Removing Dropplets, using Hugo with Netlify"
author: "claudia"
date: 2019-02-14T00:00:30-05:00
---

I've really struggled with finding a blogging set up that I like. I've been looking for one that is easy to work with, works well, and doesn't cost a lot of money. I have a bunch of blog posts written, in markdown, so the ability to port over my existing work easily is a huge plus. I've messed around with a bunch of options, like:

* wordpress
  * not as technical as I want
  * less customizable (this may have changed since the last time I used it because it's been years)
* svbtle
  * too much work to port over my other blog posts
  * costs money
* Dropplets (I used this until this new change)
  * spammed me with emails to change my password
  * the way I had set it up also needed me to ftp files over to a server to host them, which was tedious and doesn't work as well when I travel with a different laptop.
  * overall felt less nice to work with, but used markdown so I could use all my blog posts

After doing some research I figured I'd mess around with [Hugo](https://gohugo.io/) which is a really easy to use framework for building static websites. All I needed to do was `brew install` it, run a few commands to get it up and running, set up a git submodule for my theme and then run the server locally, and I had a blog! It reads in markdown files, so I was able to port over my old markdown posts easily into the format that hugo expects and voila!

[Hugo Quickstart](https://gohugo.io/getting-started/quick-start/)

Great, now I had a server running locally but needed to figure out the best way to host it and have my blog live on the ~ web ~. I found [Netlify](https://www.netlify.com/), and this specific post on combining [Hugo with Netlify](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/). I created a Netlify account, hooked it up to my Github, set up my builds and eventually after a bunch of failures was able to get my static site building and deploying to a custom netlify subdomain on pushes to my remote master branch in Github. Super cool! Now I can trigger a deploy every time I merge a new change. This fits into my Github workflow, and I have version control for my blog posts. No more FTP-ing text files.

Last but not least, I needed to figure out how to get my domain to link to this new beautiful blog I had up and running. I followed the documentation on setting up a [custom domain](https://www.netlify.com/docs/custom-domains/), and added a CNAME record for my new subdomain. It took a bit for it to show up but now my new Hugo blog is showing up on my blog subdomain!

I'm really excited about this. The ability to switch themes easily is really nice, plus I can keep all of my blog posts in markdown in Github and use the same workflow I do for work. Hopefully this new set up is going to convince me to write more blog posts this year!
