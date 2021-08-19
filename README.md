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

 - **`git add`** --- *adds files to the staging area.* **(do not use alone)**
	 - **`.`** --- *adds all files to the staging area.*
	 - **`<filename>`** --- *adds filename to the staging area.*
	 - **`<filename1> <filename2>`** --- *adds filename1 and filename2 to the staging area.*

 - **`git commit`** --- *commits changes from staging area.* **(do not use alone)**
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

 - **`git switch`** --- *allows you to switch your current HEAD branch.* **(do not use alone)**
	 - **`<branchname>`** --- *switches from your current branch to the branchnames*
	 - **`<remotebranchname>`** --- *creates a new local branch from the remote branch of the same name and it upstreams.*
	 - **`-c <branchname>`** --- *creates a new local branch and switches to it.*

 - **`git checkout`** --- *allows you to switch your current HEAD branch.* **(do not use alone)**
	 - **`<branchname>`** --- *switches from your current branch to the branchname.*
 	 - **`-`** --- *HEAD goes newest commit in the history. **(it may be in another branch!)***
	 - **`-- <filename>`** --- *reverts filename to the current HEAD **(not the newest commit!)***
	 - **`head <filename>`** --- *reverts filename to the current HEAD **(not the newest commit!)***
	 - **`head~<number>`** --- *HEAD goes number before commit.*
	 - **`<commithash>`** --- *HEAD goes commithash.*
	 - **`<tagname>`** --- *HEAD goes tagname.*
	 - **`<remotename>/<branchname>`** --- *HEAD goes branch head of remote repository.*

 - **`git restore`** --- *reverts unstaged changes.* **(do not use alone)**
	 - **`<filename>`** --- *reverts unstaged changes in the filename to the HEAD in current branch .*
	 - **`--source head~<number> <filename>`** --- *reverts unstaged changes in the filename to the specific commit but keeps changes in the staged area. **(do not use if not really needed)***
	 - **`--staged <filename>`** --- *unstages filename.*

 - **`git reset`** --- *unstages files that are in staged area.*
	 - **`<commithash>`** --- *It will remove commits and messages back to commithash also unstage if there is any file in staged area but it will not touch anything saved in the directory so, your files will not be changed from their last saved version.*
	 - **`--hard <commithash>`** --- *It will remove commits, staged and unstaged changes back to commithash.*
