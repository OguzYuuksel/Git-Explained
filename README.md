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

## Remarks
- *HEAD usually refers to a branch, not a specific commit, branch refers to a commit point.*<br />
  <img src="https://github.com/OguzYuuksel/Git-Explained/blob/main/Assets/headRefersToBranch.png?raw=true" width="400"><br />
- *Detached head can refer a commit.*<br />
  <img src="https://github.com/OguzYuuksel/Git-Explained/blob/main/Assets/detachedHead.png?raw=true" width="400"><br />
- **Remote Tracking Branch**: *It means GitHub branch. it is shown `<remotename>/<branch> | (origin/master)`.*<br />
- **Gists**: *It is a pastebin for GitHub, you can make it public or private.*<br />
- **Github Branch Protection**: *It protects your master branch, you can't commit or merge anything without pull request. Checkout `Repository Settings -> Branches`.*<br />

- > ### Feature Branch Workflow<br />
  > - *All development should be on separate branches*<br />
  > - *Treat master branch as the official project history.*<br />
  > - *Multiple teammates can collaborate on a single feature and share code back and forth without polluting the master branch.*<br />
  > - *Master branch won't contain broken code.*<br />

- > ### Pull Requests<br />
  > 1. *Do some work locally on a feature branch.*<br />
  > 2. *Push up the feature branch to Github.*<br />
  > 3. *Open a pull request using the feature branch just pushed up to Github.*<br />
  > 4. *Wait for the PR to be approved and merged. If needed start discussion on the PR.*<br />
 
- > ### Semantic Versioning<br />
  > `2.4.1` *means majorRelase.minorRelease.patchRelease*<br />
  > **Major Release**: *Significant changes that is no longer backwards compatible.*<br />
  > **Minor Release**: *New functionality added but everything is backwards compatible, new feature is optional.*<br />
  > **Patch Release**: *Bug fixes, small changes.*<br />

- > ### Tags<br />
  > Tags are generally used for Semantic versioning in master branch.<br />
  > 1. **Lighweight tags**: Just a name and label that points to a particular commit.<br />
  > 2. **Annotated tags**: Includes author's name, email, creation date and tagging message.<br />
  
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

&nbsp;
> ## Revert vs Reset
> If you are working with a team and also one of your colleague is working in the same repository in his local, you should use **revert**, because deleting a history from a repository may cause complexity to keep code sync.
 - **`git reset`** --- *unstages files that are in staged area.*
	 - **`<commithash>`** --- *It will remove commits and messages back to commithash also unstage if there is any file in staged area but it will not touch anything saved in the directory so, your files will not be changed from their last saved version.*
	 - **`--hard <commithash>`** --- *It will remove commits, staged and unstaged changes back to commithash.*

 - **`git revert`** --- *creates new commit by undoing a specific commit and both commits stays in the history.* **(do not use alone)**
   - **`<commithash>`** ---
   - **`head~<number>`** ---

&nbsp;
> **Fast Forward Merge**: Simplest merge, applies automatically without any conflict.<br />
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

 - **`git stash`** --- *saves uncommitted changes (saved or staged) in the branch.*
 	 - **`list`** --- *lists all stashes[`<branchname> <lastcommithash> <lastcommitcomment>`] in order(new first, old last).*
  	 - **`clear`** --- *removes all stashes in the list.*
  	 - **`drop stash@{<number>}?`** --- *removes stash from the list.*
	 - **`pop stash@{<number>}?`** --- *applies last stash to the current branch and removes it from stash list.*
	 - **`apply stash@{<number>}?`** --- *applies last stash to the current branch and keeps stash in the list.*

 - **`git clone <url>`** --- *clones master branch of remote repository to your local directory and upstreams it.*

&nbsp;
> ## Initializing Remote Repository
> *First be sure that you are in a local repository `git status` if not, create a local repository `git init`. Then write following*<br />
> `git remote set-url origin git@github.com:OguzYuuksel/<project_name>.git`<br />
> *Now your local repository is connected to the cloud repository, you can check it out by writing `git remote`*

 - **`git remote`** --- *prints remotename of your current repository.*
 	 - **`-v`** --- *prints cloud url of your current repository.*
  	 - **`add <remotename> <url>`** --- *connects cloud repository to your local repository.*
  	 - **`rename <oldname> <newname>`** --- *renames your remotename.*
	 - **`remove <remotename>`** --- *disconnects cloud repository from your local repository.*

 - **`git push`** --- *pushes your streamed current branch to the cloud branch(Remote Tracking Branch).*
 	 - **`<remotename> <branchname>`** --- *pushes local branchname to the branchname of remotename.*
  	 - **`-u <remotename> <branchname>`** --- *pushes local branchname to the branchname of remotename and sets upstream to it.*
  	 - **`<remotename> <localbranchname>:<remotebranchname>`** --- *pushes localbranchname to the remotebranchname of remotename.*
	 - **`<remotename> <tagname>`** --- *pushes tagname to th remotename.* **`git push` doesn't transfer your tags to the remote server!**
     - **`<remotename> --tags`** --- *pushes all tags to the remotename.*

&nbsp;
> ## Fetch vs Pull<br />
> ### Fetching<br />
> - Downloads the latest information from remote branches, updates the remote tracking branches with the new changes, doesn't merge any changes onto your local repository.<br />
> - Safe to do at anytime.<br />
> - It lets you see what others have been working on, without merging those changes into your local repository.<br /><br />
> ### Pulling<br />
> - Downloads the latest information from remote branches, updates the current branch with the new changes by merging them in.<br />
> - It may result in merging conflicts.<br />
> - `git pull` = `git fetch` + `git merge`.<br />
> - **Not recommended if you have uncommitted changes!**
 - **`git fetch <remotename>`** --- *updates remote tracking branches of remotename.*
 	 - **`<branchname>`** --- *updates remote tracking branchname of remotename.*

 - **`git pull <remotename> <branchname>`** --- *updates remote tracking branches of remotename and merging it in your branchname branch of local repository.*
