---
layout: post
title: "Git Started"
modified:
categories: GitIt
excerpt:
tags: []
image:
  feature: 
  teaser: githubLogo.png
  thumb: githubLogo.png
ads: false
date: 2015-10-04T13:43:58-07:00
---

#Git to branching#

Branching is one of the most amazing tools you have with git. It's essentially, version control inside of version control. What does that mean? Let's say you that all (the important stuff at least) your code is working properly, and there is a feature that you really want to implememnt but you're not sure that it will work. 

You're worried that playing with working may mess up the whole project. You begin to make local copies of the repo so you don't risk breaking your working code, but now it's not tracked by git. Let's say the feature you decided to implement works and you want to set the new version to include the updates you just made. Now you have to go back and try to track all the changes you made, copying and pasting all that back into the master repo. 

In that process you end up breaking your code. Luckily, you created a bunch of the local, working, copies but you still face the same copy and paste dilemna. The solutions to this is git branching this allows you to create all those local copies (and push them to your git repo as a different branch) and them merge them with your master branch, when you have them working. If you don't get them working you can either just leave the branch for later work or delete it. 



Step 1: `$ git branch ` - this will tell you which branches you have created and which branch you are currently on.

Step 2: `$ git checkout -b [the name of your new branch (no whitespace)]`

You can continue  