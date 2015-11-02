---
layout: post
title: "GIT STARTED WITH GIT"
modified:
categories: Git, Github, VCS
excerpt: So moving on, there are bunch of tutorials out there on using Git but many are quite convoluted with stuff you don't need right away.
tags: [git, github, version control, CLi]
image:
  feature: 
  teaser: githubLogo.png
  thumb: githubLogo.png
ads: false
date: 2015-10-30T13:43:58-07:00
---

So "Git", is a version control system for software engineering. It was designed by Linus Tovalds, the or the 'Linux' guy. I'll explain it in a couple different in terms of problems it helps to solve:

####1. Version Control:
Say that you get you project to a working state and you want to save it and use it now, before you break it again. Also, you still have some features to add but again, you don't want to risk breaking your already working code. Maybe one way you'd account for this is to just create a bunch of local copies of your working code on your hard drive or a few different places. So when you break your code, working on that new feature or refactoring, you can just go back to one of 50 copies of your working. If the new feature works and that ends up being version 1.2, recurse!

####2. Working in teams:
Think about #1. It'd suck pretty bad if every time you want to add or change a feature of your team's project, everyone one had to carry around a copy of the working project on a flash drive. Then, when you end up having to **copy and paste** your code into the current version -because of course, this is all supposed to happen asychronously - they ended up changing stuff that they didn't say they were going to touch but ended up having to do so in order to get their feature working. Also, imagine that everyone has to document, **every single change to every single file** and you'd have to possibly review each of those changes before you can even get to making your own, so that you don't end up with conflicting code. We're not gonna get into package management or scaffolding, but let's just agree that with projects this day in age, there's so many tools out there that we don't know absolutley **everything** that is happening, especially in development. Long story short, this is a **shitty** workflow (sort of).

####TL:DR:
Basically, Git allows you do all the stuff above in a more automated manner. So instead of worrying about the mutiple copies, the documentation of changes...worry about your team's Git workflow, which mostly includes all this stuff. Alright, if I've made this concept any more confusing you'll get when you've got a few projects under your belt.

So moving on, there are bunch of tutorials out there on using Git but many are quite convoluted with stuff you don't need right away. While you'll eventually understand it if you continue to work through it I think they could do a much better job at stripping down to basics first. This is going to be a series of posts tyring to hash out basics that will help make the more complex stuff easier to handle as your workflow needs it. 

**The first thing is that you'll learn this stuff much easier if you actually apply it to a workflow. Also, we're going to assume that you already have a few things already setup:**

- We're going to apply this to Github's version control service. So you should have a Github account (it's free)
- We're going to be using and **sh** or "shell" CLi so you should have **bash** (packaged with OSX) or **zsh**... installed
- Next you need to have some basic command line interface (CLi) knowledge, specifically `cd` (change directory) and `ls` (list directory contents)
- You need know the different uses of `cd` in terms of navigating and creating directories your system's directories

**I've not tried it out but I believe codecademy.com has a tutorial on the CLi**


####A few more things to note:
- That this aticle specifically will be a combination of using the GUI (not the Github GUI) and command line
- I'm not yet going to explain `branch`, `checkout`, `pull`, `--rebase`, `diff`, `hist`...those will come in the future
- This all, will be demostrated in a workflow that help to understand the commands. But within any organization, project, team... your Git workflow will differ

**NOTE: To do some of this stuff you may have to use the code editor Vim so I'm going to write the instruction below and you will have to refer to them if there is a step where I tell you to do so.**

####Using Vim (be very careful here):
Note: Look at the status bar at the bottom to see what mode you're in
- Hit `a` to enter into 'insert mode' so you can type stuff
- Type the stuff your want (you must use arrow keys to move around)
- Hit `esc` to get out of 'insert mode'
- Then type a `:` - (`shift :`)
- Then `w` then `q` then `enter`

####I'm going to explain how to: 
- `fork` - a project or **repo** (Github repository) to your Github profile
- `git clone` - the repo to your computer 
- Check the `git status` - of the repo after you've made changes to it's files
- Stage or `git add` - the changes to be committed
- `git commit` - or save those changes to make them Github ready
- `git push` - those commited changes to your now forked repo

####But first, a bit of setup and for that you will :
1. From the CLi `git config --global user.name "FIRSTNAME LASTNAME"`
2. Then `git config --global user.email "example@gmail.com"`

##Here we go!

####Forking the Repo:
1. From the github.com page of the repo you want to fork, click `Fork` button under the thumbnail of your profile pic
2. The you'll get a pop-up with options of where you want to for it to. Click on your profile picture...***FORKED!***

####Clone the Repo:
1. From the CLi, navigate to the folder where you want to store the repo you just forked
2. Navigate back to the forked repo in your own Github profile and copy the URL
3. From the CLi prompt `[SOMESTUFFHERE]$ ` - type - `git clone [PASTE THE URL HERE]`
  - **ex:** `git clone https://github.com/Shinobi881/Stakes-is-High`
4. BAM!!! REPO CLONED!!!
5. Now is a good time to - `cd` - into the repo you just cloned and - `git status` -, no changes yet

####Make some changes:
1. From this point you can navigate to and open the repo however you feel comfortable
2. Right now just make a **VERY** small change to any file you choose and save it 

####Stage changes and commit:
1. Go back to the CLi where you should be in the directory of your cloned repo
2. `git status` - to see the **VERY** small change you just made (it shows changes made from commit to commit)
3. `git add [THE CHANGED FILE, VERBATIM]` - or - `git add .` - to stage ALL the files you changes (optional)
4. `git commit` - **Read below and follow Vim instructions above**
  - This will send you to Vim to enter your commit message
  - Keep it concise and descriptive of you changes
  - Once you exit and save from Vim BAM!!! COMMIT DONE!!!

####At this point we've:
1. We've `Fork`ed - a repo to work on ourselves
2. `git clone` - to copy it locally 
3. `git add` - to stage the changes for committing
4. `git commit` - to save the changes for committing

####Time to push the changes to Github:
1. `git push origin master`
- This saves the changes to your Github profile
- Publishes to your commit history (as long as it's a public repo)
- Compares changes against the master of the upstream repo

**Next up will be branching with Git**
