# git-learn

dummy repo to learn advance git commands

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

**git branch branch-name**: creates a local branch named "branch-name"
**git push origin branch-name**: creates a remote branch name "branch-name". You can now see the branch named "branch-name" in the github repo branches dropdown.
NOTE: You can't push a branch to origin without making its local branch first, which should have the same name.

#### changing/checking out branches:

**git checkout branch-name**: changes branch to "branch-name"
**git checkout -b branch-name**: creates a branch named "branch-name" and then switches to it.

#### deleting branches:

**git branch -d branch-name**: deletes the existing local branch named "branch-name"
**git branch -D brnach-name**: force delete existing local branch named "branch-name" regardless of merge status. equivalent to git branch --delete --force branch-name
**git push origin -d branch-name**:deletes from remote branch
