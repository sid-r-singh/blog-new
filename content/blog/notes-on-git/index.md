---
author: "Sidharth"
title: "Notes on git from a course I took on Coursera"
date: "2021-07-16"
description: "Deep dive into git clone & remote repos"
tags: ["git"]
categories: ["Notes on git"]
aliases: [""]
ShowToc: true
TocOpen: true
---

## Folders & locations

The working tree contains the project files for a single commit, the staging area holds a list of files that will be included in the next commit, the local repository contains all of the commits of the project. On a local computer, a project directory contains the working tree as well as a hidden .git directory. The staging area and local repository are located in this directory. 

## Remote repositories

The remote repository contains the commits of the project on a remote server. By convention, remote repository names end with ".git". A typical URL for a remote repository hosted on GitHub can be [https://github.com/sid-r-singh/blog-new.git](https://github.com/sid-r-singh/blog-new.git) . Notice the ".git" added to the end of the URL to signify that this is a remote repository.

If you already have a local repository with commits that you want to push to a remote repository, you can use the `git remote add` command. This command adds information about the remote repository to the local repository (linking them).
The two repositories can then be synchronized using aliases instead of URLs.

As an example, let's say that we have an existing local repository named X, containing commits that we would like to push to a remote repository. We can log into GitHub and create a new repository named X. Then from our existing local repository, we execute the `git remote add` command. In this example, we name our remote repository origin and we specify the URL copied from GitHub. 

## Clones

The name for the remote URL is created when you execute git clone. To understand this better let's clone a repo & then change into the repo's directory.
```bash
git clone https://github.com/sid-r-singh/firebase-auth.git
cd .\firebase-auth\
```

{{< figure src="images/git-clone.jpg" caption="Output of git clone command" >}}

Now in order to get info about remote repositoy, let's execute ```git remote -v``` where we have used the verbose flag (`-v`) to get more detailed information.

Here is the output:
{{< figure src="images/git remote output.jpg" caption="Output of git remote command" >}}
```bash
🚀  git remote -v
origin  https://github.com/sid-r-singh/firebase-auth.git (fetch)
origin  https://github.com/sid-r-singh/firebase-auth.git (push)
```

Thus the name "origin" for the remote URL was created when we executed git clone.