![Git](https://i.ibb.co/YdgkwXY/download.jpg)

# :computer: Git-Cheatsheet :hammer_and_wrench:
Code snippets which detail the fundamental syntax and concepts available in [Git](https://git-scm.com/)

## Table of Contents 📖
1. [Introduction](https://github.com/Sammy-Nyakabau/Git-Cheatsheet#introduction)
2. [Creating Snapshots](https://github.com/Sammy-Nyakabau/Git-Cheatsheet#creating-snapshots-pushpin)
3. [Browsing History](https://github.com/Sammy-Nyakabau/Git-Cheatsheet#browsing-history--)
4. Branching and Merging
5. Collaboration
6. Rewriting History

---

### Introduction
>Git is a distributed revision control and source code management system with an emphasis on speed. Git was initially designed and developed by [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds) for Linux kernel development. Git is a free software distributed under the terms of the GNU General Public License version 2. This cheatsheet explains how to use Git for project version control in a distributed environment.

---

### Creating Snapshots :pushpin:
-  Basic workflow of staging content and committing it to your history

#### Initializing a repository :paperclip:
```git
git init
```

#### Staging files :paperclip:
```git
git add file1.js                # Stages a single file
git add file1.js file2.js       # Stages multiple files
git add *.js                    # Stages with a pattern
git add .                       # Stages the current directory and all its content
```

#### Viewing the status :paperclip:

```git
git status                      # Full status
git status -s                   # Short status
```

#### Committing the staged files :paperclip:

```git
git commit -m “Message”         # Commits with a one-line message
git commit                      # Opens the default editor to type a long message
```

#### Skipping the staging area :paperclip:

```git
git commit -am “Message” 
```

#### Removing files :paperclip:

```git
git rm file1.js                 # Removes from working directory and staging area
git rm --cached file1.js        # Removes from staging area only 
```

#### Renaming or moving files :paperclip:

```git
git mv file1.js file1.txt 
```

#### Viewing the staged/unstaged changes :paperclip:

```git
git diff                        # Shows unstaged changes
git diff --staged               # Shows staged changes
git diff --cached               # Same as the above  
```

#### Viewing the history :paperclip:

```git
git log                         # Full history
git log --oneline               # Summary
git log --reverse               # Lists the commits from the oldest to the newest 
```

#### Viewing a commit :paperclip:

```git
git show 921a2ff                # Shows the given commit
git show HEAD                   # Shows the last commit
git show HEAD~2                 # Two steps before the last commit
git show HEAD:file.js           # Shows the version of file.js stored in the last commit 
```

#### Unstaging files (undoing git add) :paperclip:

```git
git restore --staged file.js    # Copies the last version of file.js from repo to index 
```

#### Discarding local changes :paperclip:

```git
git restore file.js             # Copies file.js from index to working directory
git restore file1.js file2.js   # Restores multiple files in working directory
git restore .                   # Discards all local changes (except untracked files)
git clean -fd                   # Removes all untracked files 

```

#### Restoring an earlier version of a file :paperclip:

```git
git restore --source=HEAD~2 file.js
```
##### **[Back To Top :arrow_up:](https://github.com/Sammy-Nyakabau/Git-Cheatsheet#table-of-contents-)**
---

### Browsing History  📌