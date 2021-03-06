---
layout: post
author: Mohamed Wael Khobalatte
category: technology
date: 2012-09-20 14:20:40
summary: A look at the tech stack of The Escaped. 
title: Web Development for the Poor - How The Escaped Was Made
---


The launch of The Escaped has been a success. We have received overwhelming support from friends and colleagues, and we plan to make the experience even better. In the continued spirit of sharing, this article will describe how we built The Escaped. I will go over which technologies we used across the web stack and why we chose them. The Escaped is open source, and you can always take a look at the [source code](http://github.com/theescaped/theescaped.github.com) for more details about how some part of the site works. 

The Escaped is hosted on Github Pages and runs on [Jekyll](http://github.com/mojombo/jekyll), a static site generator written in Ruby. Given that Jekyll was made by one of the co-founders of Github, they made a decision to run Jekyll in their servers, giving you the possibility to push your files and expect a smooth site generation process. This is a powerful idea, because it means a simple Git push is enough to deploy your website and serve your readers. It also frees you from the need to maintain a database, which seems, after some thought, to be unsuitable for something as simple as an article. 

Originally, writing for The Escaped necessitated both a Github account and knowledge of Git, the powerful source control management tool. This meant that only people with a background in web development could write for us. To mitigate this, I started working on a custom solution, a small Ruby on Rails app in fact, that provides a simple interface to our Github repository that people with no knowledge of Git can use. It would have achieved this by making frequent API calls to Github. At the same time, I became aware of another very similar project called [Prose](http://prose.io) that was underway, and I grew fond of the its elegance and its simpler approach to solving the same problem. Eventually I abandoned my increasingly complex solution for Prose. 

We now use a modified version of Prose to publish articles to The Escaped. Being a backbone app, Prose is almost entirely client side, as opposed to my own custom solution which would have required server side processing. The only server side we run is a simple application, [Gatekeeper](http://github.com/prose/gatekeeper), which validates users on the server because Github won’t allow us to implement its OAuth Web Application Flow on the client side, apparently for security reasons. Given how light the job of this app is, it will probably never go beyond what Heroku offers for free, so we are hosting it there. We are rather pleased with this arrangement so far. 

The nice thing about this setup is its simplicity and its potential to scale. Our only financial commitment is around 180 dhs a year for the domain name. Traffic load handling is solid, since it is delegated to Github servers, and service uptime is, well, identical to that of Github, which provides us with a substantial advantage.  

Evidently, to write for The Escaped, we require a Github account, which you can make in few seconds. Once we add you as a member of The Escaped on Github, you are good to go. No other knowledge is necessary. Of course if you happen to enjoy web development, we welcome pull requests to enhance the entire experience. 

Your feedback is most welcome. 
