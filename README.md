![Git](https://i.ibb.co/YdgkwXY/download.jpg)

# :computer: Git-Cheatsheet :hammer_and_wrench:
Code snippets which detail the fundamental syntax and concepts available in [Git](https://git-scm.com/)

## Table of Contents 📖
1. [Introduction](https://github.com/Sammy-Nyakabau/Git-Cheatsheet#introduction)
2. [Creating Snapshots](https://github.com/Sammy-Nyakabau/Git-Cheatsheet#creating-snapshots-pushpin)
3. [Browsing History](https://github.com/Sammy-Nyakabau/Git-Cheatsheet#browsing-history--)
4. [Branching and Merging](https://github.com/Sammy-Nyakabau/Git-Cheatsheet#branching--merging--)
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

#### Viewing the history :paperclip:

```git
git log --stat                  # Shows the list of modified files
git log --patch                 # Shows the actual changes (patches)
```

#### Filtering the history :paperclip:

```git
git log -3                      # Shows the last 3 entries
git log --author=“Sammy”
git log --before=“2020-11-17”
git log --after=“one week ago”
git log --grep=“GUI”            # Commits with “GUI” in their message
git log -S“GUI”                 # Commits with “GUI” in their patches
git log hash1..hash2            # Range of commits
git log file.txt                # Commits that touched file.txt
```

#### Formatting the log output :paperclip:

```git
git log --pretty=format:"%an committed %H"
```

#### Creating an alias :paperclip:

```git
git config --global alias.lg "log --oneline"
```

#### Viewing a commit :paperclip:

```git
git show HEAD~2
git show HEAD~2:file1.txt       # Shows the version of file stored in this commit
```

#### Comparing commits :paperclip:

```git
git diff HEAD~2 HEAD            # Shows the changes between two commits
git diff HEAD~2 HEAD file.txt   # Changes to file.txt only
```

#### Checking out a commit :paperclip:

```git
git checkout dad47ed             # Checks out the given commit
git checkout master              # Checks out the master branch
```

#### Finding a bad commit :paperclip:

```git
git bisect start
git bisect bad                    # Marks the current commit as a bad commit
git bisect good ca49180           # Marks the given commit as a good commit
git bisect reset                  # Terminates the bisect session
```

#### Finding contributors :paperclip:

```git
git shortlog
```
#### Viewing the history of a file :paperclip:

```git
git log file.txt                   # Shows the commits that touched file.txt
git log --stat file.txt            # Shows statistics (the number of changes) for file.txt
git log --patch file.txt           # Shows the patches (changes) applied to file.txt
```

#### Finding the author of lines :paperclip:

```git
git blame file.txt                 # Shows the author of each line in file.txt
```

#### Tagging :paperclip:

```git
git tag v1.0                       # Tags the last commit as v1.0
git tag v1.0 5e7a828               # Tags an earlier commit
git tag                            # Lists all the tags
git tag -d v1.0                    # Deletes the given tag
```


##### **[Back To Top :arrow_up:](https://github.com/Sammy-Nyakabau/Git-Cheatsheet#table-of-contents-)**
---

### Branching & Merging  📌
#### Managing branches :paperclip:

```git
git branch bugfix                  # Creates a new branch called bugfix
git checkout bugfix                # Switches to the bugfix branch
git switch bugfix                  # Same as the above
git switch -C bugfix               # Creates and switches
git branch -d bugfix               # Deletes the bugfix branch
```

#### Comparing branches :paperclip:

```git
git log master..bugfix             # Lists the commits in the bugfix branch not in master
git diff master..bugfix            # Shows the summary of changes
```

#### Stashing :paperclip:

```git
git stash push -m “New tax rules” # Creates a new stash
git stash list                    # Lists all the stashes
git stash show stash@{1}          # Shows the given stash
git stash show 1                  # shortcut for stash@{1}
git stash apply 1                 # Applies the given stash to the working dir
git stash drop 1                  # Deletes the given stash
git stash clear                   # Deletes all the stashes
```

#### Merging :paperclip:

```git
git merge bugfix                  # Merges the bugfix branch into the current branch
git merge --no-ff bugfix          # Creates a merge commit even if FF is possible
git merge --squash bugfix         # Performs a squash merge
git merge --abort                 # Aborts the merge
```

#### Viewing the merged branches :paperclip:

```git
git branch --merged               # Shows the merged branches
git branch --no-merged            # Shows the unmerged branches
```

#### Rebasing :paperclip:

```git
git rebase master                 # Changes the base of the current branch
```

#### Rebasing :paperclip:

```git
git cherry-pick dad47ed           # Applies the given commit on the current branch
```
##### **[Back To Top :arrow_up:](https://github.com/Sammy-Nyakabau/Git-Cheatsheet#table-of-contents-)**
---

### Collaboration  📌