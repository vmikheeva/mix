## Master
## =======
## Branch A


## Content
* Basic dev-process scenarious with git commands
* Additional commands
* Useful links

## Basic dev-process scenarious with git commands

### View current configuration 
git config --list

### Configure your user credentials to be used by default in git commands
git config --global user.name "your name"

git config --global user.email "your email"

### Start working with repository: clone repository to get the latest version of the integration branch
git clone https://github.com/username/RepoName.git

cd RepoName

git checkout Branch_Name

### Clone repository together with its submodules
git clone --recursive https://github.com/username/RepoName.git

or

git clone https://github.com/username/RepoName.git

cd RepoName

git submodule update --init --recursive

### Create new feature-branch
git branch [dev_branch]

### Switch to created feature-branch to start working on it
git checkout [dev_branch]

### Check status after making modifications
git status

gitk

### Add modifications to the staging area to prepare for commit
git add -A

### Commit with the description-message
git commit -m "Description of the commit"

### Push feature-changes into remote repository (on feature-branch)
git push -u origin [dev_branch]

### Incorporate latest changes from the Integration branch into the feature-branch
git pull origin main_branch

### Merge local modifications into the integration branch
git checkout main_branch

git merge [dev_branch]

### Rebasing on a branch
git checkout experiment

git rebase master

// First, rewinding head to replay your work on top of it...

// Applying: added staged command

// Then, go back to master and do fast-forward merge:

git checkout master

git merge experiment

https://git-scm.com/book/en/v2/Git-Branching-Rebasing

## Additional commands
### List existent branches and see the active branch
git branch

### To discard all changes in working directory
git checkout -- .

### To discard changes in specific files
git checkout -- [file]...

### Set link to remote repository
git remote add origin https://github.com/username/RepoName.git

### Cache the password in windows
git config --global credential.helper wincred

### Stashing work-in-progress before doing commits and merge
git add -A

git stash

https://git-scm.com/book/en/v1/Git-Tools-Stashing

### Recover the latest stashed version
git stash list

git stash apply

### See the latest 6 commits description
git log -6 --pretty=oneline

### Exit git log, when it contains many lines
Press [q]+[Enter]

### Create lightweight tag
git tag [v1.4-descr]

https://git-scm.com/book/en/v2/Git-Basics-Tagging

### Create annotated tag (preferred)
git tag -a [v1.4-descr] -m "[description for version 1.4]"

### Create "backdated" tag
git tag -a v1.2 [commit-hash-tag]

### Push specific tag
git push origin [v1.4-descr]

### Push all local tags
git push origin --tags

### Checkout tag into the new local branch (do not push this branch!)
git checkout -b [temp-branchname] [tagname]

### Replace the tag's description
git tag [tag-name] [tag-name]^{} -f -a

### Rename a tag (replace the old one)
git tag [new-tag-name] [old-tag-name]

git tag -d [old-tag-name]

git push origin :refs/tags/[old-tag-name]

git push --tags

### Move tag to a newer commit (replace the old one)

1) Delete the tag on the remote before you push

git push origin :refs/tags/[tagname]

2) Replace the tag to reference the most recent commit

git tag -fa [tagname]

3) Push the tag to the remote origin

git push origin [tagname]

## Useful links
### Git cheat-sheet
https://services.github.com/kit/downloads/github-git-cheat-sheet.pdf

### Git reference documentation
https://git-scm.com/docs

### Pro Git Book
https://git-scm.com/book/en/v2

### Git simple guide
http://rogerdudler.github.io/git-guide/

### Easy to use, though quite powerful, merge tool
http://winmerge.org/
