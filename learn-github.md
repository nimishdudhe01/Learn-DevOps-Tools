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
