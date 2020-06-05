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
