# Create local branch daves-branch that tracks remote branch origin/daves-branch
	git checkout --track origin/daves-branch

# Merge development into master
1. Make sure your local versions of master and development are not ahead of the remote versions. If they are, pause and think.
2. Bring your local branches up to date
	- `git checkout development && git pull && git checkout master && git pull`
3. Merge development into master
	- `git checkout master && git merge development`

# Prune remote branches
	git remote prune origin --dry-run
	git remote prune origin

# Delete local branches
	git branch -d branch_name
	git branch -D branch_name

# Nice git log
	git log --all --decorate --oneline --graph

# Useful config
NOTE: Use with care! Think especially of the credentials.
```.gitconfig
[credential]
	helper = store

[alias]
	lg1 = log --graph --abbrev-commit --decorate --format=format:'%C(cyan)%h%C(reset) - %C(white)(%ar)%C(reset) %C(magenta)%s%C(reset) %C(white)- %an%C(reset)%C(green)%d%C(reset)' --all
	lg2 = log --graph --abbrev-commit --decorate --format=format:'%C(white)%h%C(reset) - %C(white)%aD%C(reset) %C(white)(%ar)%C(reset)%C(white)%d%C(reset)%n''          %C(white)%s%C(reset) %C(white)- %an%C(reset)' --all
	lg = !"git lg1"
[user]
	name = Usually your actual name, often only you first name. Ultimately up to you.
	email = Can be your email if you want. I often do "name@computer-name"
```

# History of a single file
	git log --follow -p -- path-to-file
