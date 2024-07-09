
# General
`git help <command>` Get manual for command
`git init` Initialize local project to use git
`git status` Check the status of repository
`git log` Check the commit logs

`git config --global --list`
`git config --global -e`


`git add <file(s)/folder/.>` Stages the files
`git commit` Commits the staged files
+ `-m "<commit-message>"` Add commit message directly
+  `--amend` Prompts to change latest commit message
`git checkout <id/branch-name>` Move to the `id` commit or `branch-name`
`git revert <id>` Creates a new commit that reverts the changes made in `id`
`git reset --hard <id>` Deletes all commits after `<id>`

# Branches

`git branch` Lists all existing branches
`git branch <name>` Creates branch from current commit
`git checkout -b <name>` Creates branch from current commit and moves to it
`git branch -D <name>` Delete branch
`git merge <target-branch>` Merge `<target-branch>` into current branch
+ `--no-ff` (No Fast Forward) Keeps the other branch commits visually
+ By default, if there are no new commits on target branch, all the commits will be copied
# .gitignore

```sh
# Comment line

# Ignore specific file
file.txt

# Ignore entire directory
logs/

# Ignore file by extension
*.log

# Ignore file by extension in specific directory
logs/*.log

# Negation pattern. Include specific file or directory that would be ignored
*.env
!special.env

# Ignore nested files
**/*.log

# Ignore files only in the root directory
/file.txt
```

# Remote

+ `git remote add <remote-target> <url>` Connect local repository to remote `URL`

> [!TIP]
> Recommended to use `origin` as `remote-target` name.
> `origin` is like a shortcut for `<url>`

+ `git push <remote-target> <branch-name/tag>`
	+ `--tags` Pushes all the tags
	+ `:<tag-name>` Removes tag from remote
+ `git pull <remote-target> <branch-name>` Pulls the changes locally
	+ `git pull --rebase <remote-target> <branch>` Pulls and also does rebase
+ `git fetch` Updates the references between remote and local
+ `git clone <URL> [<folder-name>]`
+ `git remote` Check list of all connected remote repositories
+ `git remote get-url <name>` Check the URL of repository


# Renaming files


# Git config

`git config --global user.name "<username>"`
`git config --global user.email "<email>"`
Signing commits: [Github GPG](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key)


`git config --global alias.<custom-command> "<full-command-without-git>"`

#### Diff/Merge tool
+ `git config --global merge.tool <tool-name>`
+ `git config --global mergetool.<tool-name>.path "full/path/to/tool.exe`
+ `git config --global mergetool.prompt false`

+ `git config --global diff.tool <tool-name>`
+ `git config --global difftool.<tool-name>.path "full/path/to/tool.exe`
+ `git config --global diftool.prompt false`

+ `git diff` Resume for differences
	+ `HEAD` Compare working directory with last commit
	+ `--staged HEAD` Compare staging area with the last commit
	+ `-- <file-name>` Compare only the `<file-name>`
	+ `<commit-id/branch-name/tag> <commit-id/branch-name/tag>` Compare 2 mentions
	+ `<commit-id> HEAD` Compare selected commit with last commit
	+ `HEAD HEAD^` Compare last commit with last commit - 1
	+ `master origin/master` Compare local master with remote
	
`git difftool` Will open the configured/predefined tool






# Rebase

> [!NOTE]
> Copies the target branch onto current branch, then applies current branch commits


+ `git rebase <branch-name/id>`
+ `git rebase --abort`
+ `git rebase --continue` Used after solving conflicts

# Stash

+ `git stash` (`save` by default) Saves the local tracked changes into a stash
	+ `git stash save "<stash-name>"` Creates and names the stash
	+ `git stash -u` Stashes local changes including untracked files
	
+ `git stash list` Shows the available stashes
+ `git stash pop` Applies the following commands
	+ `git stash drop` Removes latest stash
		+ `<stash-id>` Removes selected stash
		+ `git stash clear` Removes all stashes
	+ `git stash apply` Moves latest stash into working directory and prints `git status`
		+ `<stash-id>` Moves the selected stash into working directory

+ `git stash show` Shows the changes of latest stash
	+ `<stash-id>` Shows the changes of selected stash

+ `git stash branch <branch-name>`
	+ Creates new branch
	+ Applies stash
	+ Deletes stash


# Tags

+ `git tag <tag-name>` Creates *lightweight* tag
	+ `-a <tag-name>` Creates annotated tag. Will get asked to add description
		+ `-f <commit-id>` Moves tag to another commit
	+ `<commit-id>` Applies tag to targeted commit
	+ `-m "<description>"` Add description directly
+ `git tag --list` Lists tags
+ `git show <tag-name>` Shows details about tag
+ `git tag --delete <tag-name>` Removes tag

# Git areas

Untracked - Working area - Staged area - Repository - Remote


# Revert

# Reset