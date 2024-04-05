# Learning Git

### So, What is Git?
Git is a distributed version control system that tracks changes in any set of computer files, usually used for coordinating work among programmers who are collaboratively developing source code during software development. Git's goals include speed, data integrity, and support for distributed, non-linear workflows.

We'll be using git for learning git, using practicals.

Content of this tutorial:
- Create repositories locally
- Change histories and branches
- Merging and diffing among branches
- Cloning and creating GitHub Repositories
- Branching, forking, and pull requests
- GitHub issues for collaboration


## Starting a Software Project
When working with a codebase/something of that sorts, reproducibility and tracking, and collaboration depends on good use of version control. When a distributed version control system like git is used, users also utilize a source code repository to allow others to discover and interact with a codebase more easily. Among these, GitHub is the most popular one.

#### Status, Adding, Committing

The basics of working with versions and changes in a project:
- init
- status
- config
- add
- commit
- log

```
git config --global user.name "Nimish Dudhe"
git config --global user.email "20cs3043@rgipt.ac.in" 
```
The above commands are used to setup the identity of the local user who is working on the repository.
These changes can be found in the .git/config file.

If you want to set identity only for a specific repository, you need to omit the --global argument.

```
git init
```
The command above initializes a Git repository in the current directory.r

```
tree .git
```
The command above will print a tree of the directory structure of the .git directory.

```
git status
```
This will show the status of the current git repository, If there are files of this repository are modified or if there are new files added, If there are changes(commits) pending to be committed, etc.

```
git add *
```
This command will add all the files(except hidden ones) to the repository. The files added become ready for committing. 

```
git commit
```
This command opens up the default configured text editor for writing commit message and description and commits the work(changes) which has been added to the repository.

```
git commit -m "Added learn-github.md file."
```
The above command will make a commit of the previous changes in the repository. After committing, the `git status` command would show "Nothing to commit". It is because there are no untracked changes in the repository as of this moment.

```
git diff
```
This command helps compare different versions of same file maintained by the repository. Just like `git status`, git diff too outputs nothing after a recent commit has been made.

```
git log
```
There's something knowns as log of the repository, which can be looked at using the command above. After the word commit, there are these special strings which are unique identifier for the commits.

#### Version History & Branches
```
git checkout <commit-id>
```
This command allows you to view your repository in a previous state without needing to create a new branch or modify an existing branch. It basically takes the repository back in time to a previous commit of your choice.

```
git branch
```
This lists out all the available branches in the repository. To change the branch you want to work on, you need to use the `git checkout <branch-name>` command.

```
git branch <new-branch-name>
```
This would create a new branch to work on from the current state. To work with the new branch you just made, just use the command `git checkout <branch-name>`.

```
git branch -B <new-branch-name>
```
This makes a new branch and automatically does checkout that branch so that you can start working with the new branch immediately.

```
git log --graph --all
```
This outputs all the commits from all the branches in a graph structure.

```
git log --oneline --all
```
This outputs all the commits from all the branches in separate single lines.

```
git branch -D <branch-name>
```
This command is used to delete an existing branch.

```
git branch -B <new-branch-name> <existing-branch>
```
What this does is creates a new branch from the existing branch that we specified. And performs checkout on the new branch so we can immediately start working on the new branch.

#### Merging & Diffing

```
git diff
```
This gives a diff of the non-committed files with the previous commit.

```
git diff <commit-id-x> <commit-id-y>
```
This gives the diff between any 2 commits that you want to differenciate among.

```
git merge <commit-id-x> <commit-id-y>
```
This merges two different branches together into a single branch. 

### Local vs Remote Branches
A local branch is the one which exists only on your local machine whereas a remote branch exists in a repository(most commonly referred to as `origin` by convention) and is hosted on GitHub.
Once you have committed changes to your local branch, you can push the local branch to the remote repository (origin) using the `git push <remote> <local>`. Then, others will be able to see your code.
```
git push origin <local-branch-name>
```

#### Using Remote Branches
```
git branch -r
```
To view a list of all remote branches in the project, use this command.

```
git branch -a
```
This lists all the branches in a repository, Including remote ones.

```
git checkout -b <local-name> <remote-name>
```
The above command shall be used if you need to work with a remote branch. This will create a local copy of the remote branch and will automatically checkout the branch you just specified.

```
git fetch origin '+refs/heads/*:refs/heads/*'
```
This can be used to create a local branch of all the avaiable remote branches. And will be named automatically according to the branch name.

