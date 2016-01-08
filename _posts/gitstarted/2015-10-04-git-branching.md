---
layout: post
title: "Git to branching"
modified:
categories: Git, Github, VCS
excerpt: Branching is one of the most amazing tools you have with git. It's essentially, version control inside of version control.
tags: [git, github, version control, CLi]
image:
  feature: git-beyond6.jpg
  teaser: 
  thumb: 
ads: false
date: 2015-10-31T13:43:58-07:00
---


Branching is one of the most amazing tools you have with git. It's essentially, version control inside of version control. What does that mean? Let's say that all (the important stuff at least) of your code is working properly, and there is a feature that you really want to implememnt (if you can get it working before shipping) but you're not sure that it will work. 

You're worried that messing around with working code may mess up the whole project. You begin to make local copies of the repo so you don't risk breaking your working code, but now it's not tracked by git. Let's say the feature you decided to implement works and you want to set the new version to include the updates you just made. Now you have to go back and try to track all the changes you made, copying and pasting all that back into the master repo. 

In that process you'll likely end up breaking your code. Luckily, you created a bunch of the local, working, copies but you still face the same copy and paste dilemna. The solutions to this is branching. Branching allows you to create all those local copies (and push them to your git repo as a different branch) and then merge them with your master branch when you have them working. If you don't get them working you can either just leave the branch for later work or delete it. The code on your master branch still works. You only have to be upset about spending time on a scrapped feature and without the worry of broken code. 

There are also some very specific work

If you need to brush up on your Git basics see my previous post at: [Git Started With Git](http://shinobi881.github.io/git,/github,/vcs/git-it-started/)

**Step 1:** [check branches] `$ git branch ` - this will list the branches you have created and which branch you are currently on.

**Step 2:** [create new branch] `$ git checkout -b [the name of your new branch (no whitespace)]` Create a your new branch - Note:It's good practice to prefix branches with common tags such as `feat/newfeature`.

**Step 3:** [commit, push] `(feat/newfeature)$ git push origin feat/newfeature` - This assumes that you want to commit and push your new branch to your Github.

**Step 4:** [merge branch] `(master)$ git merge feat/newfeature` 
When you have your new feature working and you want to merge it with your master, make sure that:

- You have commited your changes
- `$ git checkout master` - checkout to your master branch (or other branch you want to merge to)
Once, you're back on the branch you want to merge to run the merge command above. This will make you master branch identical to `feat/newfeature` branch. 

**Some good practices:**
- prefix your branch names with tags `feat`, `refactor`, `bug`, `fix`, `style`...so other collaborators have an idea what your're working on. This also helps to keep me focused on my current feature.
- It's good practice to always work in a new branch and to keep your `master` branch clean and working.
- As always commit often.

**Additional branching features:**
- Get all the branches on a project: `$ git fetch origin` or `$ git fetch upstream`
- Clone directly from a branch: `$ git clone -b [branch name] [link to repo]` 
