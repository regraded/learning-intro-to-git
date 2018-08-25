# Intro to working with Git

## Git Basics

There are three basic stages/principals of git. 
1. **Working Directory**: This is where all our unsaved fies and dirs live
2. **Staging Area**: Where files/dirs go, when we are getting ready to commit them to the repo. 
3. **Repository**: Where all our snapshots are stored (files we have comitted into the repo)

**Basic starting commands**
`git init <repo-name>`     create new repo.
`git status`               shows status of files in working vs staging area. Red files = not in staging. Green = in staging. 
`git add <file>`           adds files to staging area. 

## Creating a repo
1. Create a new project folder `mkdir <folder>`
2. Change into directory with `cd <folder>`
3. Create a new repo with `git init`

## Staging files 
- **Add** files from working `git add <file>`
- **Remove** files from staging with `git reset HEAD <file>`

### Adding multiple files at onces
- You can use wildcards to add certain file types eg `git add *.html`
- You can add all files using `git add -A`

## Comitting files
Commit staged files to the repo by using `git commit -m "Message"`. You can remove the -m flag, which will then open a editor, where you can enter a more detailed message. However, if you message is simple, then using the `-m` flag allows you to add a short message.

The general rule for phrasing a commit message is `<Present tense word> <Short description> 
For example
> Add README.md
> Update README.md
> Fix markdown in README.md
> Add all HTML files

## View commit history
You can show the repo commit log by entering `git log`. 

## Branches
Branches are like copies. Dupicating the source branch (usually master), so that you can work on a copy of the source, changing files, comitting etc, without having to commit directly into you priary (master) branch. 
This is perfect for creating new features or testing new code. Once you are happy with your new feature, you can choose to merge the branch back into the master (or visa versa)

### List Branches
List all repo braches with `git branch`. 
`*` indicates the the current branch

### Create (Checkout) a new branch
To create a new branch, we checkout an entire branch using `git checkout -b <new branch name>`

### Changing between branches
Change between branches using `git checkout <branch-name>`

### Merging a branch
So, you're ready to merge your new feature back into the master branch. When you merge two branches together, you are merging from the destination branch. 
As in, if you want to merge your new features branch back with your master branch, you need to be in the master branch, and merge "IN" the feature branch. 

1. Switch to the master branch with `git checkout master`
2. `git merge <branch to merge into current branch>`

### Removing a branch
Typically best practice is to keep branches around. They dont take up much space so there is no need to remove unless absolutely necessary. 

If you need to remove a branch, you do `git branch -d <branc-name>` (-d for destroy)

## Pushing to github
To push to github, you need to set your local repo to have an origin repo:
1. `git remote add origin <URL>`
2. verify with `git remote -v`
3. `git push --set-upstream origin master`

## Creating SSH pair so you arent prompted for username/password
Best is to follow this article: https://help.github.com/articles/connecting-to-github-with-ssh/

**Generate new SSH key and add to the ssh-agent**
1. `ssh-keygen -t rsa -b 4096 -C "SSH Key label"`
2. Save in default location
3. Add passphrase
4. Start the ssh-agent `eval "$(ssh-agent -s)"`
5. Add your new ssh key to the agent `ssh-add ~/.ssh/id_rsa`
6. Copy the public key (view the key using `cat ~/.ssh/id_rsa.pub`)
7. Add it to the github keys page
8. Test conneciton with `ssh -T git@github.com`

