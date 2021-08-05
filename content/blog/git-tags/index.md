---
author: "Sidharth"
title: "Git tags"
date: "2021-07-18"
description: "Understanding git tags"
tags: ["git"]
categories: ["Notes on git"]
aliases: [""]
ShowToc: true
TocOpen: true
---

A tag is a reference or bookmark to a specific commit. Git supports two types of tags: 
1. lightweight
2. annotated

They differ by the amount of meta data they store.

## Annotated tags
These tags allow storing extra meta data such as: the tagger name, email, and date & most importantly a tagging message. These tags can be signed and verified with GNU Privacy Guard (GPG). Since all these information has to be stored somewhere, git stores these as full objects in git database i.e they consume space (though quite insignificant). It’s generally recommended to create annotated tags so that you can have all these information.

### Cretaing annotated tags
In the following command,
```bash
git tag -a v1.9 -m "Software version 1.9"
```
- `-a` flag tells git to create an annotated tag
- `-m` specifies a tagging message, related to the tag. Just like commit messages, if you don’t specify any message, Git launches the default editor for you to type it in.

## Lightweight tags
As the name suggests, these tags don't store any mata data & that's why aptly named as lightweight (from storage perspective).

### Creating lightweight tags
To create a lightweight tag, just don’t supply any of the -a, -s, or -m flags. You need to provide a tag name only.
```bash
git tag v2.0
```

## Listing tags
At any point of time if you wish to see/list all your tags you can type `git tag`. Sample output:
```bash
$ git tag
v1.0
v2.0
v3.0
```

## Searching for tags
What if you become the next Linus Torvalds & say you have 999 tags in you repo ? Don't worry you can use
`git tag -l "v1.3.5*"` to list all tags starting with "v1.3.5". Sample output:
```bash
$ git tag -l "v1.8.5*"
v1.3.5
v1.3.5-rc0
v1.3.5-rc1
v1.3.5.1
v1.3.5.2
v1.3.5.3
v1.3.5.4
v1.3.5.5
```

**Note:** If yo are using a wildcard pattern to match tag names, the use of `-l` or `--list` flag is mandatory.