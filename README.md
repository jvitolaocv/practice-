# repoPractice
A small repo for practicing with CLI Git commands.
At this point in your training, you should have...
* Read through chapters 1 - 3 of the Git-scm book
* Taken some brief notes on some Git commands.
* Setup the Git CLI on your machine
* Watched the linked youtube video demonstrating the usage of the Git CLI
You should now play around with the Git commands yourself by using this testing repo.


### Getting Started
You can start by pulling down this repo to your local machine. Navigate to the desired directory within your Linux machine or Ubuntu subsystem (make sure it hasn't been initialized with a repo previously) and running the command "git pull origin master". What did the CLI print to the screen after you executed this command?
* If the terminal output something similar to "fatal: could not read from remote repository" then you got the correct output!
  * If you run the command "ls" within your directory, do you see any of the files from the repo in your directory? The answer should be no if you got the earlier output!
  * This is because you have not INITIALIZED the repo, so Git has no idea what master branch you're referring to when you try to pull the data down!
* Try this command after following the next section and observe how the output changes.

### Initializing
You have two common ways of initializing your repo; you can run the command "git init" which will create an empty repo in the directory you're in (and then proceed to push it to your Github account so it becomes public) or you can clone from an existing repo (which is the more common way).
* The latter approach is what we will be focusing on.
* If you view any Github page, you should see a section at the root of the repo to "clone or download"; this will give you two further options:
  1. Downloading will allow you to download all the files in the repo as a .zip file, and then unzip them (which will work the same way but isn't the desired way of doing this).
  2. Cloning will give you an https or ssh link; the https link can be pasted in after a "git clone" command, while the ssh link will require you to generate an ssh key and upload it to your Github account.
* For now, if you don't have your ssh key setup yet, you can copy the https link and run the command "git clone" followed by the link you copied within your desired local directory; you should then see the files that were in this repo now on your local machine!
  
### Pulling
Pulling is done with the "git pull" command, and it is done to pull and merge new changes from the repo you are now tethered to (note: you can run "git fetch" as well to pull the new changes down WITHOUT automatically merging them).
* If you run "git pull origin master", this would pull down (and merge) any new changes from the master branch. If you try this command right now, you will receive a message in the terminal similar to "this branch is currently up to date".
* It is generally safe to run "git pull" regardless of the automatic merging; if there is a merge conflict, you will be notified and will have to manually resolve them to integrate the new changes in.

### Branches
So far, you have only been working with the "master" branch: this is the main branch for the repo, where all changes are eventually merged into. We create other branches so we can make changes to the code and integrate them into this master branch.
* The "git checkout" command followed by a branch name will switch you to an already existing branch (assuming you have already created one).
* Try running the command "git checkout newBranch". What does the terminal output following this command?
  * The terminal should say something along the lines of "error: pathspec 'newBranch' did not match any file(s) known to git" but what does this mean?
  * This means that this branch does not currently exist, even if you already created it on Github!
  * If you supply the "-b" parameter right after "checkout" but before the branch name, it will actually create this new branch and switch to it (but it will still not be tracking the branch on Github; to do this, you must then run the command "git pull origin newBranch", assuming the branch name on Github matches the one on your local machine).
* You can check what branch you are on alongside any changes that need to be stashed/committed with the command "git status".
* As a general rule of thumb, it is easier to make the Github branch and local branch names the same to avoid any little problems/errors that may arise when working with Git.

### Pushing
Pushing is done with the "git push" command, and it is done to push all your work to the branch you are on.
* The general workflow for pushing your work will be as follows:
  1. Run "git status" to see what work you have to submit and what branch you are on.
  2. Run "git add ." to add all changed files to what you plan to commit.
  3. Run "git commit -m" followed by a one sentence textual reason (in quotation marks) as to what changes you made.
  4. Run "git push origin" followed by the name of the current branch you are on and plan to push to.

### Wrap Up
You may download this repo and make any changes you want to the existing files; you may even add more if you want! Use this test repo to play around with some of the other commands that you took notes on from the Git-scm book and get a good feel for how to use this powerful tool. As a reminder, the normal workflow of using Git each day will usually be:
  1. Navigate to the desired directory.
  2. Run "git init" to create a brand new project or "git clone" followed by a ssh or https link to the repo you want to pull the existing work down from (if you're starting a new project).
  3. Run "git checkout -b" followed by your new branch name, and then proceed to create a branch with the same name on the Github repo (unless you're working with an existing branch, then just switch to the branch with "git checkout" followed by the existing branch name.
  4. Run "git pull origin" followed by the branch name to pull down any new changes.
  5. Make changes to the code.
  6. Run "git add ." to add all files to what you're about to push.
  7. Run "git commit -m" followed by a one sentence textual reason (in quotation marks) as to what changes you made.
  8. Run "git push origin" followed by the name of the current branch you are on and plan to push to.


## IMPORTANT - PLEASE READ THIS!!!!
##### DO NOT PUSH TO THE MASTER BRANCH!!!!!!
* Always ensure which branch you are on with "git status" and make sure you are not pushing to the master branch.
* Github is good for uploading new files and changes to existing files; it is NOT easy to delete files and clean up the branches!
##### IF YOU PUSH TO THE MASTER BRANCH, YOU WILL CAUSE A LARGE MESS THAT WILL BE INCREDIBLY DIFFICULT TO FIX AND YOUR COWORKERS WILL ALWAYS REMEMBER IT!!!
##### FURTHERMORE, IF YOU PUSH WITH THE "-f" OR "--force" PARAMETERS, YOU COULD OVERWRITE ALL EXISTING CHANGES AND POTENTIALLY BE FIRED!!!
