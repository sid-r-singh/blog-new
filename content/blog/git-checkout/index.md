---
author: "Sidharth"
title: "Git Checkout"
date: "2021-07-19"
description: "Understanding git checkout"
tags: ["git"]
categories: ["Notes on git"]
aliases: [""]
ShowToc: true
TocOpen: true
---

## What happens in a checkout ?
Checkout is related to branches of a repository and does two main things.
First, it switches the current commit (which is the commit that the HEAD reference points to) to the checked out branch label or commit. For example, if you are on the master branch and then checked out the feature branch, the HEAD reference changes 
- from - pointing to master branch label
- to - pointing to the feature X branch label

The second thing that checkout does is, it updates the working tree with the files from the checked out commit. It can be compared to (loosely) changing the working directory (`cd`).

## Creating & checking out a branch
To combine creating and checking out a branch into a single command,
you can use the `-b` option with git checkout. For example `git checkout -b feature` creates a branch 'feature' & then switches to it (checkout). It fails if a branch with same name already exists. 