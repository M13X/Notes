
# General
`git init` Initialize local project to use git
`git status` Check the status of repository
`git log` Check the commit logs


`git add <file(s)/folder/.>` Stages the files
`git commit` Commits the staged files
`git checkout <id/branch-name>` Move to the `id` commit or `branch-name`
`git revert <id>` Creates a new commit that reverts the changes made in `id`
`git reset --hard <id>` Deletes all commits after `<id>`

# Branches

`git branch` Lists all existing branches
`git branch <name>` Creates branch from current commit
`git checkout -b <name>` Creates branch from current commit and moves to it
`git branch -D <name>` Delete branch
`git merge <target-branch>` Merge `<target-branch>` into current branch
# .gitignore

# Remote

`git remote add <local-name> <url>` Connect local repository to remote `URL`

> [!TIP]
> Recommended to use `origin` as `local-name`.

`git push <local-name> <branch-name>`
`git pull`
`git clone <URL> [<folder-name>]`
`git remote` Check list of all connected remote repositories
`git remote get-url <name>` Check the URL of repository
# Git config

`git config --global user.name "<username>"`
`git config --global user.email "<email>"`

Signing commits: [Github GPG](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key)