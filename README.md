# git-learn

dummy repo to learn advance git commands

## Working Areas:
- Working directory : This is your local directory where you make the project (write code) and make changes to it.
- Staging Area (or index) : this is an area where you first need to put your project before committing. This is used for code review by other team members.
- Local Repository : this is your local repository where you commit changes to the
project before pushing them to central repository on Github. This is what is provided by distributed version control system. This corresponds to the .git folder in our directory.
- Central Repository : This is the main project on the central server, a copy of which
is with every team member as local repository.

## Creating:

- from scratch(two ways)::no work done on the project till now:
  - 1st on local system and then on github
  - 1st on github and then on local system
- from existing:
  - from your own existing system files
  - from others repo
    - you are a collaborator
    - you have no access

**git init**:

-

## Adding/Staging Files:

- git add file-name
- **git add .**: adds all files to staging area
- **git add a.txt b.txt c.txt**: adds the given files

## Unstaging files:

- git reset -- <path>
- git restore: made changes to files>not staged>git restore>undo the changes
- git restore --staged : made changes to files>staged>run command> unstage the changes>changes will remain, just will be removed from the staging area

## Commiting files:

- git commit -m "commit-message"
- git commit -a -m "commit message": adds the files and commits them
- **git commit --amend -m "new-commit-message"**: creates a new commit with all the files same but with a "new-commit-message"

## Remotes:

- **git remote -v**: shows existing remote
- **git remote add remote-name remote-url**: adds github "remote-url" to the list of existing remotes and names it "remote-name". NOTE: both fetch and push urls are set
- **git remote set-url remote-name remote-url**: changes the url of the existing remote "remote-name" to "remote-url"
- **git remote rm remote-name**: removes "remote-name" remote from the list of existing remotes. NOTE: It does not delete the remote repo, only the remote and its references from local repo

## Branching:

#### Listing branches:

**git branch** :

- lists all local branches.
- (\*)rred and the one in green is the current _local_ branch.
- The branches in white are local branches

**git branch -a** :

- lists all the branches (local+remote)
- (\*)rred and the one in green is the current _local_ branch.
- The branches in white are local branches
- The branches in red are remote branches

**git branch -r** :

- lists all the remote branches.
- The branches in red are remote branches

#### creating branches:

- **git branch branch-name**: creates a local branch named "branch-name"
- **git push origin branch-name**: creates a remote branch name "branch-name". You can now see the branch named "branch-name" in the github repo branches dropdown.
  NOTE: You can't push a branch to origin without making its local branch first, which should have the same name.

#### changing/checking out branches:

- **git checkout branch-name**: changes branch to "branch-name"
- **git checkout -b branch-name**: creates a branch named "branch-name" and then switches to it.

#### deleting branches:

- **git branch -d branch-name**: deletes the existing local branch named "branch-name"
- **git branch -D brnach-name**: force delete existing local branch named "branch-name" regardless of merge status. equivalent to git branch --delete --force branch-name
- **git push origin -d branch-name**:deletes from remote branch



## Downloading data from remote:

- **git fetch <remote-name>**: checks "remote-name" for new data. But does not change a thing in the local repo. So, can execute as many times w/o any consequences. NOTE: Its like apt-get upgrade
- **git pull <remote-name> <remote-branch-name>**:pull not only downloads new data; it also directly integrates it into your current working copy files. NOTE: Effectively its a git fetch followed by git merge
- **git pull --rebase <remote-name>**: ![Rebase](rebase.png)
git 



## Sending data to remote:
- **git push origin**: will push changes from all local branches to matching branches the origin remote.//tried but doesn't work
- **git push origin master**: will push changes from the local master branch to the remote master branch. Can be run while inside any branch.
- **git push origin master:staging** will push changes from the local master branch to the remote staging branch if it exists.



## Misc:

- **git config --global help.autocorrect 1**: activate autocorrect
- **git log**: show commit history
- **git status**: current status of files
- **git checkout <SHA>**: revert repo to a previous commit having unique id SHA. Find the SHA from git log
