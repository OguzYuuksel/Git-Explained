## Initialization 
 - When you are inside a new directory check `git status` if this directory has a repository.
 - If not use `git init` command to create a local repository.

## Committing Rules
 - **Commit only for one feature, fix or update**
 - Describe your commit comments in imperative mood. 
 - Commit titles should be less than 50 character and it must summarize changes.
 - If commit titles not enough to describe all changes, you may use next lines to explain your changes.

> ~~footer added~~ 
> add footer

> ~~I fixed navigation bug~~ 
> fix navigation bug

## Useful Commands
 - **`git init`** --- *creates repository in the current directory.*
 - **`git status`** --- *checks git status in the current repository.*

 - **`git add`** --- *adds files to the staging area.*
	 - **`.`** --- *adds all files to the staging area.*
	 - **`<filename>`** --- *adds filename to the staging area.*
	 - **`<filename1> <filename2>`** --- *adds filename1 and filename2 to the staging area.*

 - **`git commit`** --- *commits changes from staging area.*
	 - **`-m "commit title"`** --- *allows us to pass in an inline commit title, rather than launching a text editor.*
	 - **`-am "commit title"`** --- *adds all changed files to the staging area and commits them. It doesn't work for the files which are never added to the staging area before.*
	 - **`--amend`** --- *change the comment of previous commit or add current staging files to the previous commit.*

 - **`git log`** --- *lists all history of commits in the current branch.*
	 - **`--oneline`** --- *lists oneline summary of all history of commits in the current branch.*

 - **`git branch`** --- *lists all of the branches in our local repository.*
	 - **`-v`** --- *lists all of the branches with their last commits in our local repository.*
	 - **`<branchname>`** --- *creates a new branch called branchname in our local repository.*
	 - **`-d`** --- *deletes branchname in our local repository.*
	 - **`-m <newbranchname>`** --- *renames current branch with newbranchname in our local repository.*
	 - **`-r`** --- *lists remote branches that are fetched into our local repository.*
	 - **`-u <remotename>/<branchname>`** --- *sets upstream branch to the your local branch.* **(both must have the same name!)**

 - **`git switch`** --- *allows you to switch your current HEAD branch.*
	 - **`<branchname>`** --- *switches from your current branch to the branchnames*
	 - **`<remotebranchname>`** --- *creates a new local branch from the remote branch of the same name and it upstreams.*
	 - **`-c <branchname>`** --- *creates a new local branch and switches to it.*

