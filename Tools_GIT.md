

# References #
  * GIT - Fast Version Control System http://git-scm.com/
  * GIT from bottom up: http://ftp.newartisans.com/pub/git.from.bottom.up.pdf
  * tips: http://nuclearsquid.com/writings/git-tricks-tips-workflows/
  * Training: http://techbus.safaribooksonline.com/video/software-engineering-and-development/version-control/9781449304737

# Definition #
GIT is a content tracking system, if a file metadata has changed GIT won't impact its status
∂
# Setting Up Git and Configuring Git #
```
git config --global color.ui "auto"
export EDITOR=notepad2.exe
ssh-keygen -t rsa -C"<email>@<domain name>.<tld>" # you need to create public and private key -C is a comment
```

# Best practice #
  * do atomic operations, it gives a better visualisation of what is occurring
    * Don't change code and relocate it in one step (32:30)
    * e.g. rename the files, then refactor the content of the files in two separate commits
  * Rebase once a day to keep you code up to date
  * Categorize by lifetime (branch)
    * Short lived
      * bug fix
    * Feature
      * small, medium change
    * Release
      * all the work

## naming convention ##
  * TAGNAME: capital letters and underscores for spaces (e.g. HEAD, PROD, 0.1)

# Basic tasks: edit, push, pull #
  * Edit a file a file and push it
```
echo this is our first file >> afirstfile.txt
git add .
git commit -m 'A description of the change'
git push
```

  * The other side should pull the new change
```
git pull
#if the system the system asks for a branch because it is lost do this:
git branch --set-upstream <name of the branch> origin/<name of the branch> 
#the system should show: "Branch <branch name> set up track remote branch timsidea form origin"
#the branch is bidirectionally linked by now
#this process is made to ensure we are cautious and we do mean it (the bidirectional link)
```

  * get a specific version of a branch
```
git log
git checkout <hascode of the commit> #you need to checkout a branch
```

  * Start a new branch from the current one
```
git branch <new branch name>
git checkout <new branch name>
```

  * Start a new branch from master and push the new branch on the remote server
```
git checkout -b <new branch name> master
git push origin <new branch name>
```

  * check the git log as a graph
```
git log --graph --pretty=oneline
```

  * rebase

```
git add .

```
# Three Stage Thinking, The Git File Workflow and Speed #

![http://wiki.doomicile.de/_media/howto/vcs/git-transport.png](http://wiki.doomicile.de/_media/howto/vcs/git-transport.png)

## Create a first GIT repository ##

```
get init ourfirstrepo
ls -al # file is empty
git status
    * INFO: untracked files are not in the staging area

touch index.html
git add index.html
git status 
    * from untracked to "changes to be committed"

git commit
    * don't need a filename

git commit -m 'Added a second html file'
git add . #add all files including subdirectories

git add . -A # add ALL files, deleted, etc.
git add .  # deleted and renamed files won't be part fo the addition
```

## GIT file workflow (34:00) ##

### ignore, remove, move files (39:00) ###
```
mkdir ignore-remove-move-files
cd ignore-remove-move-files
touch myapp.log
touch myapp2.log
touch myapp3.log
touch index.php
mkdir subfolder
```

```
touch .gitignore
vi .gitignore

*.log # any log is ignored
**/*.log # for any subdirectory don't include .log files
target # remove the directory named target

git status #the log files have been ignored fro the git status
```

```
git config --global alias.ignorechanges = update-index --assume-unchanged
git config --global alias.noticechanges = update-index --no-assume-unchanged
```

```
git push
```

### speed ###

# Cloning Repositories #

```
git clone ssh://user@server:project.git
git clone user@server:project.git
```

## clone a project on github ##
```
git clone https://github.com/matthewmccullough/hellogitworld.git hgw2
ls -al | grep .git
```

# command composition, storage, hashes #

## command composition ##
commands are composed of sub commands not API

### Plumbing and Porcelain ###
  * Plumbing is the low level utilities
  * Porcelain is the set of useful commands

## storage ##
  * Typical SCMs use delta storage
  * GIT us a Directed Acyclic Graph (DAG)
    * directional nodes and there is no cycle possible A => B => C => A
  * centralised VCSs use sequential revision numbers
  * GIT uses 40 hex characters for the hash

## log ##
```
git log
git log --pretty=oneline

git log 583..583^ # show the previous one
git log 583..583~3 # show the three last ones
git log 583-6..583-4 # showform 6 back to 4 back
git log HEAD^^^..HEAD # show three last ones up to the point of HEAD
git show # last commit + delta in a diff format of all the files

git commit -a -m 'small change' # add and commit at the same time
```

check the
```
cd .git
cat HEAD # it contains refs: refs/heads/master - this the path to the branch
cd refs/heads
ls
cat master # it contains the hash of the branch
```

# Branches #
  * What do cheap branches?
  * Safe experiment
  * When should you branch? the answer is always branch
  * Branches isolate volatile work
  * We've always wanted to branch often it's just been too expensive

A successful Git branching model: http://nvie.com/posts/a-successful-git-branching-model/

## Create a branch ##
```
git remote -v
git pull
```
either use
```
git branch matthewsidea # create the branch
git checkout matthesidea # switch to the new branch
```
or
```
git checkout -b matthewsidea # create and switch to new branch
```

```
git branch #show all branches
```

make some changes in files, then commit
```
vi sample4.txt
git add sample4.txt
git status
git commit
git status
git push
```

```
git push origin matthewsidea #origin is the default remote repository
git branch -a
```

18:00

```
git branch -a #all the branches available remotely and locally
git branch # all the branches available locally

git checkout a branch name #download the code locally + switch to the branch
```



```
git checkout timsidea #it will create a local branch
```


## Delete a remote  branch ##

Deleting is also a pretty simple task (despite it feeling a bit kludgy):
git push origin :<branch name>

## Delete a local branch ##

```
git branch -d <branch name to delete>
```
# Remotes #
  * Remotes area just symbolic names
  * You can have as much as you like
  * the default name is origin if you've cloned
  * remote branches are locally immutable
  * adding remotes
  * Fetching from remotes


```
git remote -v #see all the remote

git remote add <remote name> http|git|ftp://<address of the code> #create a new remote name based on a certain piece of code
```

  * Fetch
```
git fetch # plumbing command
git fetch <remote address> 
```

  * interesting file

```
cd <project directory>/.git
cat config #contains the local config of the project
```

bidirectional code transmission
  * clone
  * pull
  * fetch
## fetch ##
```
#download source code for code review
git fetch
git diff <local branch> <remote branch :e.g. timsieda origin/timsidea> # check the difference between the remote and the local code

git diff <local branch> <remote branch :e.g. timsieda origin/timsidea> --word-diff

git diff <local branch>^^ <remote branch :e.g. timsieda origin/timsidea> --word-diff #do check 1 versions before
```

  * push

# Tagging #
  * two binary steps:
    * heavy
    * lightweight
  * Tags are markers
  * true tagging and cheap tags
  * useful to visualise 'when was the latest time the code worked'
  * Tagging at each level of approval
    * Dev
    * CM
    * QA
    * Production
  * Light and object tag types (1:52)
    * comments attached on tag
    * actual objects (commit) for object tag
    * GPG signing

```
git tag <TAGNAME> # lightweight version
or
git tag -a <TAGNAME> # heavy weight with -a
```

you need to explicitly push a tag! It won't be done automatically
```
git push --tags
```

New example
```
git tag -a 0.2
git push --tags
```

## Use case about a bank (18:40) ##

The cryptographic signing piece in heavyweight tags
This is a new legally accepted way for a sign off between the teams that do things like manipulating your bank account
signing a heavy weight tags is a legally accepted way of that team has its own responsibility
the integrity of the repository, its hashing structure ensure that if someone alter a bill rate or a credit amount

Each tag can be signed off by each team by QA by financial analysis team and be part of the same commit

# MERGING #
  * taking off is important but landing is as important
  * merging a remote branch, this is called a fast-forward branch
  * conflicting mode needs some work
  * in fast-forward mode merging is done automatically

10:10 screenshot

```
git checkout master
git merge myfeaturebranch
```

process

```
#you are in branch-1 and wants to merge with branch-2
git pull #to refresh the directory, for example in the morning
git merge <the branch you want to check> 
# you might get an error message: 
## Auto-merging README
## CONFLICT (content): Merge conflict in README
## Automatic merge failed; fix conflicts and then commit the result.

#to correct the conflict:
get diff #you see the difference
```

you use either
```
git checkout --theirs -- <filename to checkout>
```
or
```
git checkout --ours -- <filename to checkout>
```

check the status of the repository
```
git status

#you should see: 
## On branch branch-1
## Unmerged paths:
## both modified:      <filename checked out>
```

now you need to add the file and commit it WITHOUT adding an automatic message
```
git add <filename checked out>
git commit
git push origin <branch name that has been changed e.g. branch-1>
```

# REBASE #

Rebase reorders the mainline commits before your branch work

Rebase changes history

Rebase simulates team members **taking turns** working (one person at a time)

13:46 screenshot

best practice: Rebase once a day to keep you code up to date

## How to understand rebase ? ##

### first user ###
```
001
git checkout master

004
echo master:rebase:user1:afile.txt >> afile.txt
git commit
add some text and save
git push
```


## second user ##
```
002
git checkout master

003 
vi newfile.txt
add some text in it
git add newfile.txt
git commit -m 'master:rebase:newfile created'

005
git fetch origin #fetch the code of user1
git merge origin/master
#now user2 sees both files newfile.txt and afile.txt into its directory
git rebase #check here it is not clear

git log --graph --pretty=oneline
or gitk #if it is installed
```

12:12 revise the presentation as it is more complicated but I am tired

```
#create three files

echo master:rebase:user1:afile01.txt >> afile01.txt
git commit
add some text and save

echo master:rebase:user1:afile02.txt >> afile02.txt
git commit
add some text and save

echo master:rebase:user1:afile03.txt >> afile03.txt
git commit
add some text and save

```

```
A possible process if you rebase and many files have been modified

git rebase HEAD^^^ -i #rebase with three versions earlier using the interactive 
#rebase stops because there is  a conflict
git status
git diff
#use either --theirs or --ours
git checkout --theirs -- <filename to checkout>
git status
git add <filename to checkout>
git rebase --continue #retry the same process again and again

#when finished
git push
#the push can be rejected because you are rewriting history
```


# undo, bonus tips #
  * undo are closing segments
  * amend **reimplements** the last commit
    * amend a bad commit message

## amend a bad commit message ##
```
git commit --amend
```

## revert **negates** one or more commits ##
logical negation of something that happened in the past

```
git revert <hash code of the commit>
#you can update the revert and maybe change its content
```

git revert for a range
```
git --revert HEAD^^^
```

## reset **erases** one or more commits ##

### reset a mistake ###

```
git reset --hard
```

```
git reset --hard HEAD^^^
```
## a tool ##
```
#come back to a perfect state
git pull origin +master:master
```
## stash  - push, pop files and move them from branches to branches ##
```
#get the locally modified files and keep them into a temporary commit
echo HELLO >> myhello.txt
git add myhello.txt
ls -al #file myhello.txt is stored in the directory
git stash
ls -al #file myhello.txt has disappeared

#checkout another branch in order to put the new file e.g. myhello.txt into another branch and remove it from the current one

git checkout <branch name e.g. branch-1>
ls -al #file myhello.txt is not existing
git stash pop
ls -al #file myhello.txt exists
```


## clean **purges** untracked files ##

```
echo this is a nice message >> file.txt
mkdir target
touch target/build.jar
git status
git clean
git clean -f #force to delete the files
git clean -f -d #force to delete the files and the directories

#note that files that are ignored in .gitignore are not part of the untracked files
```

```
echo this is a nice message >> file.txt
git clean -n #indicates what would happen if git clean is called
```

## create an alias ##
```
git config --global alias.monkey "log graph --pretty=oneline"
git monkey 
```

```
git config --global alias.dm "!git diff | mate"
git dm
#run a command that can be anything
```

```
# leave a message to another developer separate from the commit
git notes add
# edit the message for the following object

git log 
#you will have a note in the log
```

```
#how to keep empty directories pulled and pushed
mkdir test
touch test/.gitignore
git add .
git commit
git push
```

## how to "merge" only per line and not per file? ##
```
git add . -p
```

# some tools, command lines #

```
git remote show origin
```


| Issue | Resolution |
|:------|:-----------|
| git pull - You asked me to pull without telling me which branch you want to merge with,  and 'branch.master.merge' in your configuration file does not tell me, either | git branch --set-upstream master origin/master |

# GIT Hub configuration #

```
git config user.name "Abdelkrim BOUJRAF"
git config user.email "aboujraf@hotmail.com"
git config github.user Abdelkrim
git config github.token <pubic key>
```