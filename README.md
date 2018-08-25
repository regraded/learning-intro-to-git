# Working Directory
- All our unsaved code / fies and dirs.

# Staging Area:-
- Files and dirs what we choose to add to staging area.
- Move files into this area, to prep before comitting them to a repository.

# Repository:
- Where all our snapshots are stored (files we have comitted into the repo)
- 

# Commands:
git init <repo-name> //     create new repo
git status //               shows status of files in the working dir. Red files = not in the repo / not tracked
git add <file> //           adds files to staging area. 


Step 1. Create repo. git init
Step 2. Stage files. git add
Step 3. Commit staging area into repo. git commit

How to commit: 

git commit -m "Message"

Present tense word, followed by short description. Eg. Add README.md

Show the history: git log

# Adding multiple files of a certain type. 
1. Use wildcard, git add *.html

# Add all files including hidden files
git add -A 
-A = All files

# Remove files from staging area
git reset HEAD <file>


# Branches
Add a branch to create a new stream where you can create new code or test new features without comitting into your main codebase / master branch. 
If you decide you are happy with your branch, you can merge it back with your existing master branch.

- List Branches
    - git branch
    - * shows current branch

- Checkout a new branch
    - git checkout -b <new branch name>

- changing between branches
    - git checkout <branch-name>

- Merging a branch
    - git merge <branch to merge into CURRENT branch> 
    - eg. you are in feature1, you want to merge master branch into feature1 branch so you git merge master. 
    - if you wanted to merge feature 1 into master, you need to be in master branch, and then git merge feature1
    - so you are always merging from the destination branch

- Removing a branch
    - Typically you keep branches around. No need to remove unless absolutely necessary. 
    - If you need to remove a branch, you do git branch -d (d for destroy) <branch-name>
- 

