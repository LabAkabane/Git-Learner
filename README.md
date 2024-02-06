# Git Tutorials

## Git Configuration
```
git config --global user.name "example"
git config --global user.email "example@gmail.com"

# Set token remembered locally
git config --global credential.helper store
```

## Initialize a Reposotory with Git and Github
- Initialize from local
```
git init
touch .gitignore
```
Then link your local repository to your remote repository in the next step.
- Initialize from remote
    - Create repo
    - `git clone <url>`

## Push Your Changes
- Check status of the files: `git status`
- Keep track of the files: `git add .` or `git add <path/to/file>`
    - Go back from a staged to an unstaged file: `git reset HEAD <path/to/file>`
- Commit: `git commit -m "<message>"`
- Pull first:
```
# pull all changes from remote on top of your changes
git pull origin main

# keep local changes as well             
git pull --rebase origin main    
```
- Push: `git push origin main`

## Git History
- Compare local unstaged changes to recent commit: `git diff`
- See history commits: `git log`
    - To make view better: `git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"`

## Branching
- Create branch: `git checkout -b <branch>`
- Check local and remote branches: `git branch -a`
- Check only local branches: `git branch`
- Checkout branch: `git checkout <branch>`
- Fetch other branch from remote: `git fetch`
- Pull remote changes on a branch: `git pull --rebase origin <branch>`
- Push local changes on a branch: `git push origin <branch>`
- Delete branch: 
```
git branch -d <branch>        # delete local 
git push origin :<branch>     # delete remote
```
or 
```
git push origin --delete <branch>
```
- Transfer commit from 'main' to 'branch':
```
# get commit hash in main
git log

# checkout to the correct branch
git checkout <branch>

# transfer commit
git cherry-pick [hash]

# checkout back to main and delete previous hash
git checkout main
git rest --hard [hash]  

# --hard will even delete not tracked documents, use --soft if not 100% sure
```

## Ignore files already tracked and pushed to remote
[How to fix .gitignore?](https://www.codeblocq.com/2016/01/Untrack-files-already-added-to-git-repository-based-on-gitignore/)
