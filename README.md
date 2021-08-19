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

&nbsp;&nbsp;
>### Dont switch branch without committing or stashing all changes in the current branch!
> When you make changes in branch A and without committing now you want to switch branch B, these changes will come with you to the branch B. If there is conflict, terminal will print an error, if not, your changes will go unstaged area of branch B.

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

 - **`git revert`** --- *creates new commit by undoing a specific commit and both commits stays in the history.* **(do not use alone)**
   - **`<commithash>`** ---
   - **`head~<number>`** ---

&nbsp;
> **Fast Forward Merge**: Simplest merge, applies automatically without any conflict.
> **Merge Conflicts**: Terminal will open a text editor to fix conflicts after you fix them, merge will be applied.
 - **`git merge <branchname>`** --- *merges branchname to the current branch.*

&nbsp;
> ## Understanding Diffs in the terminal
> diff --git a/filename1 b/filename2  ---> **a previous, b new version**
> 
> @@ -3, 4 +3 5 @@ <br />
> -3 -> **a version starts from line 3.** <br />
>  4 -> **prints 4 line on screen.** <br />
> +3 -> **b version starts from line 3.** <br />
>  5 -> **prints 5 line on screen.** 

 - **`git diff`** --- *shows differences between current vs branch HEAD or staged area.*
	 - **`<filename>`** --- *shows filename's differences between current vs branch HEAD or staged area.*
	 - **`head <filename>?`** --- *shows differences between current vs branch HEAD.*
	 - **`--staged <filename>?`** --- *shows differences between staged area vs branch HEAD.*
	 - **`--cached <filename>?`** --- *shows differences between staged area vs branch HEAD.*
	 - **`<branchname1> <branchname2> <filename>?`** --- *shows differences between branchname1's last commit vs branchname2's last commit.*
	 - **`<commithash1> <commithash2> <filename>?`** --- *shows differences between commithash1 vs commithash2.*
	 - **`<tag1> <tag2> <filename>?`** --- *shows differences between tag1 vs tag2.*
	 - **`head@{<number1>} head@{<number2>} <filename>?`** --- *shows differences between number1 vs number2 in the Reflog HEAD (all history of HEAD).*
