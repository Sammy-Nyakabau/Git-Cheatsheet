![Git](https://i.ibb.co/YdgkwXY/download.jpg)

# :computer: Git-Cheatsheet :hammer_and_wrench:
Code snippets which detail the fundamental syntax and concepts available in [Git](https://git-scm.com/)

## Table of Contents 📖
1. [Introduction](https://github.com/Sammy-Nyakabau/Git-Cheatsheet#introduction)
2. Creating Snapshots
3. Branching and Merging
4. Collaboration
5. Rewriting History

---

### Introduction
>Git is a distributed revision control and source code management system with an emphasis on speed. Git was initially designed and developed by [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds) for Linux kernel development. Git is a free software distributed under the terms of the GNU General Public License version 2. This cheatsheet explains how to use Git for project version control in a distributed environment.

---

### Creating Snapshots :pushpin:
-  Basic workflow of staging content and committing it to your history

#### Initializing a repository
```git
git init
```

#### Staging files
```git
git add file1.js            # Stages a single file
git add file1.js file2.js   # Stages multiple files
git add *.js                # Stages with a pattern
git add .                   # Stages the current directory and all its content
```

#### Viewing the status

```git
git status      # Full status
git status -s   # Short status
```

#### Committing the staged files

```git
git commit -m “Message”     # Commits with a one-line message
git commit                  # Opens the default editor to type a long message
```

#### Skipping the staging area

```git
git commit -am “Message” 
```