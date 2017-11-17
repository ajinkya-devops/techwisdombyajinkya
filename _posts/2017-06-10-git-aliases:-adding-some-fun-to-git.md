---
layout: post
title: "Git Aliases: Adding some fun to Git"
date: 2017-06-10 08:27:18
initpath: 'assets/img/Post_Images/2017-06-10-git-aliases:-adding-some-fun-to-git/1.png'
image: '../assets/img/Post_Images/2017-06-10-git-aliases:-adding-some-fun-to-git/1.png'
description: Introduction to Git Aliases
category: 'devops'
tags:
- Git
- Aliases
- SCM
twitter_text: Introduction to Git Aliases
introduction: Introduction to Git Aliases
---

<p align="justify"><code>Git</code> is a powerful, sophisticated system for distributed <code>version control</code>. Gaining an understanding of its features opens to developers a new and liberating approach to source code management. </p>

<p align="justify">How many of you know that in Git, many powerful features are hidden behind options rather than exposed as default behavior. One such feature is <code>Git Aliases</code>. </p>


### What are Aliases?

<p align="justify">Git supports aliases so you can create your own commands that do all manner of Git magic.
In this post, we will see a selection of the more useful (or at least entertaining) aliases. </p>

<p align="justify">(All of these aliases need to be configured only once with <code>git config</code> & then you can use them FOREVER!) </p>


### Git Shorty

<p align="justify">All of you must be running git status more than any other git commands! And all thanks to the continuous evolution of Git over the years, Git's inline help has become very friendly. </p>

<p align="justify">But one of the shortcomings of Git Status is it shows very lengthy output. </p>

<p align="justify">For example, <code>git status</code> emits <code>13 lines</code> to tell me that I have a couple of staged, unstaged, and untracked changes: </p>

![placeholder](<../assets/img/Post_Images/2017-06-10-git-aliases:-adding-some-fun-to-git/2.png> "Git Aliases")


<p align="justify"><code>git shorty</code> tells me the same thing in <code>3 lines!</code> Pretty cool, isn't it? </p>

![placeholder](<../assets/img/Post_Images/2017-06-10-git-aliases:-adding-some-fun-to-git/3.png> "Git Aliases")


### Git Commend

<p align="justify">Ever commit and then immediately realize you’d forgotten to stage a file? Worry no more! </p>

<p align="justify"><code>git commend</code> quietly tracks any staged files onto the last commit you created, re-using your existing commit message. </p>

```shell
    $git config --global alias.commend 'commit --amend --no-edit'
```

![placeholder](<../assets/img/Post_Images/2017-06-10-git-aliases:-adding-some-fun-to-git/4.png> "Git Aliases")


### Git It

<p align="justify">The first commit of a repository can not be rebased like regular commits, so it’s good practice to create an empty commit as your repository root. </p>

<p align="justify"><code>git it</code> both initializes your repository and creates an empty root commit in one quick step. Next time you spin up a project, don’t just add it to version control: git it! </p>

![placeholder](<../assets/img/Post_Images/2017-06-10-git-aliases:-adding-some-fun-to-git/5.png> "Git Aliases")


### Git Grog

<p align="justify">You can customize conventional <code>git log</code> according to your convenience. </p>

<p align="justify">Here's one of the simplest way (Yes, you read it correctly!) to do that: </p>

<pre>$git config --global alias.grog 'log --graph --abbrev-commit --decorate --all --format=format:"%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(dim white) - %an%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n %C(white)%s%C(reset)"'</pre>


<p align="justify">After which you can use <code>git grog</code> & the output will be quite different than <code>git log</code>. </p>

![placeholder](<../assets/img/Post_Images/2017-06-10-git-aliases:-adding-some-fun-to-git/6.png> "Git Aliases")


### Other commonly used Aliases

<p align="justify">Here are some of the most commonly used aliases which you can set for once and then use in your git bash. </p>

```shell
    git config --global alias.co checkout
    git config --global alias.ci commit
    git config --global alias.st status
    git config --global alias.br branch
    git config --global alias.type 'cat-file -t'
    git config --global alias.dump 'cat-file -p'
```

<p align="justify">If you have some neat Git aliases of your own, share them in the comments. </p>

<p align="justify"><code>Happy Aliasing!!</code> </p>