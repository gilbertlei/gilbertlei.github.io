---
layout: post
title: Git Basics
---

Git/Github is the most popular version control system. I also use it to manage my projects as well as to collaborate with others. In this post, I will summarize some basic/important git commands.  

### How to clone a github repo to local computer?
`git clone REPO_URL`

### How to upload local changes to remote repo?
`git add FILE`   
`git commit -m "message"`   
`git push`  

### How to collaborate with others using forking?
* Firstly, fork an existing repo to get a forked copy in your private account.  
* Next, use `git clone` to create a local copy of your forked repo.
* Run below command to link local repo to the original upstream repo.  
`git remote add upstream <original_repo_URL>`  
* Then, edit local copy (add/modify/delete files).  
* After that, use above command to upload local changes to your remote forked repo.   
* Lastly, on your remote forked repo, create a `pull request`, so that your collaborators can get a notification, review the changes you made, and merge them.  

If others made changes and sent a pull request:
* You firstly need to review these changes on github and merge it.  
* Then, run below command to sync your local repo and your remote forked repo.  
`git fetch upstream`   
`git merge upstream/master`   
`git push`   

### How to collaborate with others using branching?  
* Firstly, clone the remote project repo to local.  
`git clone REPO_URL`   
* Create a new branch locally and switch to this new branch.   
`git branch BRANCH_NAME`  
`git checkout BRANCH_NAME`
* After making some changes (add/modify/delete files), push.  
`git add FILE_NAME`   
`git commit -a -m "MESSAGE"`   
`git push -u origin BRANCH_NAME`   
* Then, on github project repo, create a pull request, so that your collaborators can review the changes you have made.  
* After your collaborators reviewed and merged your pull request on github, you need to update your local master:  
`git checkout master`  
`git pull`  
* If you don't need your collaborators to review and merge on github, you can, after commit your changes, merge your branch locally:
`git add FILE_NAME`   
`git commit -a -m "MESSAGE"`  
`git checkout master`  
`git merge BRANCH_NAME`   
`git add .`   
`git commit -a -m "MESSAGE"`  
`git push`  

Other useful branching command:  
`git log --oneline --decorate`  # check where the branch pointers are pointing   
`git branch`    # show the list of all available branches   
`git branch -v` # show the last commit on each branch    
`git branch --merged`  # show all branches that have been merged. You can delete merged branches later on   
`git branch --no-merged`  # show all branches that have not been merged.   
