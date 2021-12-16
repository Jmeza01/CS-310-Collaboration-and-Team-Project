# Collaboration and Team Project
### ** Basic commands **

// start a git repository (go to folder, start bash, type this):
git init

// create .gitignore file in the current directory
touch .gitignore

// see all files in staging area (files that will be included in the commit and files that are untracked, etc..)
git status

// add index.html file to staging area
git add index.html

// add all files to staging area
git add .

// remove index.html file from staging area
git rm --cached index.html

// to see the differences between what's in the local working directory's (not yet staged changes) vs. what has been staged
git diff


### ** Commits **

// show commit history
git reflog
// get out of reflog commit history
q

// show log
git log

// show log (extended version)
git log --online --decorate --all --graph

// commit
git commit -m 'REPLACE_WITH_COMMIT_COMMENT'

// undo last commit
git reset HEAD~

// revert to earlier commit (commit number 33e5a00 - found in commit history or on github.com)
git revert 33e5a00

// remove file from LOCAL machine ONLY (removes "file.txt")
git rm file.txt

// see all commits from current branch
git log --oneline

//




### ** Branches **

// look at different branch called "login"
git checkout login

// create new branch called "module1" and switch to it (copy current code into new branch)
git checkout -b 'module1'

// show current branch and all other branches
git branch

// show differences between branches
git diff master origin/master




### ** Merge Branches **

// To update main branch with feature-1 branch, checkout main because that is the branch you want to merge into
git checkout main
// Now, merge:
git merge feature-1
// Deal with any conflicts




### ** Git Conflicts **

// After a merge, there may be conflicts
// First, fix the file that had the conflicts (delete the nonsense git generated, and delete line(s) of choice). Then commit the changes you made:
git add .
git commit -m 'fixed git conflict'
// push changes if need be
git push origin




### ** Remote **

// link local repository to remote repository on Github (requires a blank repository made on Github - ex: WeightTracker)
git remote add origin (Weight Tracker link)
// list remote repositories
git remote

// list all remote github sites configured
git remote -v

// list all remote branches
git branch -r

// push local to remote (push to main branch of InventoryManagementSys repository)
git push -u InventoryManagementSys main

// remove file from REMOTE repository ONLY (removes the file "file.txt" from github.com)
git rm --cached file.txt
(if you want to keep it locally but don't want the file on remote repos, then include it in .gitignore and commit and push)

// remove a whole folder from REMOTE ONLY (removes the folder called "myFolder" from Github.com)
git rm -r --cached myFolder/
(include in .gitignore file then commit and push)

// retrieve the updates (if any) to the remote repo on current branch, and store them in a temporary branch (such as origin/main)
git fetch

// fetch + merge from remote
git pull




### ** Ignore file in commits **

// ignore changes to ALREADY TRACKED file
git update-index --skip-worktree C:/Users/gaut2/IdeaProjects/InventoryManagementSys/src/main/java/inventory/services/DBConnection.java

// check to make sure file is ignored
git ls-files -v | grep ^S

// undo ignore and start tracking file again
git update-index --no-skip-worktree C:/Users/gaut2/IdeaProjects/InventoryManagementSys/src/main/java/inventory/services/DBConnection.java
