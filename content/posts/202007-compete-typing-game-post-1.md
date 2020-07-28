---
title: "compete - Typing Game, Post 1"
date: 2020-07-28T01:09:38+05:30
tags: ["project", "compete", "typing", "game", "interlink"]
---

 _[Github repository](https://github.com/sahilister/compete)_, 
 _[Next]() (coming on August 8th) post in the series._


Today I'm committing to working on compete. Compete is an online multiplayer typing 
game which I intend to work upon. Now that my college require me to submit a project, 
I'll work on compete.

This is first in series of posts I'll write every day having 8 in its date i.e. 8, 18, 28; updating about the status 
of work. Initial timeline is 2 months starting from July 28th, 2020 till September 
28th, 2020 (coincidentally next day of my birthday).

## Table of Content

1. [Detailed Checklist](#detailed-checklist)
2. [Thoughts and Learnings](#thoughts-and-learnings)
3. [Changelog](#changelog)

### Detailed Checklist

- [ ] Local setup
	- [ ] Keyboard character recognition
	- [ ] Error recognition and highlighting	
	- [ ] Points system
	- [ ] Text from Wikipedia API, random page
	- [ ] Add variable timers

- [ ] Multiplayer mode
	- [ ] Room creation using socket.io
	- [ ] Implement local setup for each user
	- [ ] Sync Wikipedia article
	- [ ] Implement start and timer
	- [ ] Sync timer
	- [ ] Leaderboard

- [ ] UI/UX redesign
	- [ ] Homepage
	- [ ] Match page
	- [ ] Result page

- [ ] AWS setup
	- [ ] Offload to EC2 with Elastic Beanstalk

- [ ] Add site to [compete.sahilister.tech]() 

- [ ] Add-ons
	- [ ] Authentication
		- [ ] Register
		- [ ] Login
		- [ ] Session management

	- [ ] Profile
		- [ ] Matches played
		- [ ] Matches won
		- [ ] Matches lost
		- [ ] Average words/min 

### Thoughts and Learnings

In my 3rd year of my college, we used to play 
[typeracer](https://play.typeracer.com/) a lot. We used to host room and tell 
classmates to join. Maybe that was the initial inspiration behind it. 

Through the 
project I want to work on React(for frontend), Node.js (for backend server), Express (Node.js framework), Amazon Elastic Compute 
Cloud (EC2 a virtual computer) which is fun, AWS Elastic Beanstalk (in place of Heroku, for application deployment on EC2), Socket.IO (for bi-directional communication b/w client and server) 
and maybe p5.js (for visual features).

And above all get compete with friends in typing on my personal domain at [compete.sahilister.tech]().

### Changelog

- Added introduction to project
- Added detailed checklist section
- Added thoughts and learnings section
- Added changelog section
