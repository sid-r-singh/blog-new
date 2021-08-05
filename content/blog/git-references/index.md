---
author: "Sidharth"
title: "Git references"
date: "2021-07-17"
description: "Understanding git references"
tags: ["git"]
categories: ["Notes on git"]
aliases: [""]
ShowToc: true
TocOpen: true
---

## Necessity 
References are but ways to specify a previous commit. For example, if your cat (named Kitty) plucked out keys from your keyboard, how will you scold it ? The first requirement is that of a name right ? So you'll say something like "Hey **Kitty**, how dare you do that !!!" Now comeback to git. Say you committed a file wrongly, how do you revert back to that specific commit ? The way you specify a particular commit is by using references. Using git references basically allows you to have a naming/addressing convention for your commits. In simple words references are a means using which u can say "Hey git! can you go back to that commit ?" or "Hey git! can you show me that specific commit ?"

## Head
HEAD is a reference to the current commit. It usually points to the branch label of the current branch. Further,
- it only points to the current/latest commit 
- there can be only one current commit

Due to the above reasons there is only one HEAD reference in a repository. 

## Referencing prior/previous commits

### Using ~
Referencing previous commits is easily done with  `~` character. If we execute `git show HEAD`, it will show the information for the current commit object &  it's SHA-1 hash value.

If we append a ~ to the above command, then it refers to the current commit's parent. Also `~` is equvalent to `~1`. In other words `git show HEAD~` & `git show HEAD~1` do the same thing.

In a similar manner if we execute `git show master~3` we will reference the commit which is 3 commits behind the current commit. 

### Using partial SHA-1
You can execute the command with a partial SHA-1 as well. For example `git show e0bu7x~~~` will refer to 3 commits behind '*commit with partial SHA-1 e0bu7x*'.

### Using tags
A tag is a reference to a specific commit. Say you have a commit tagged `v0.1`. Then `git show v0.1` will simply refer to that tagged commit.