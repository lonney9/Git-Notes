# Git Notes

Git Command Notes

## Push changes

```bash
git add -A ; git commit -am "Update" ; git push
git add -A ; git commit -am "Initial commit" ; git push
```

## Clone with specific SSH key (repo then knows to use this key)

```bash
git clone -c "core.sshCommand=ssh -i ~/.ssh/key1.key" git@github.com:<repo>/<repo.git>.git
```

## Reset local repo back to same as remote (lose local changes)

```bash
git fetch origin
git reset --hard origin/main
```

## Git config (sets the user that a commit appears to come from regardless)

```bash
~/.gitconfig
```

## Set name and email address

```bash
git config --global --edit
```

## Show the git user (set in ~/.gitconfig)

```bash
git config user.name
git config --list --show-origin
```

## Clear the user

```bash
git config --local credential.helper ""
```

## Clear commit history

This will clear or remove the commit history making the current commit appear as though it is the first one.

The fix pull error command will need to be run if the repo exists on another machine with out deleting and cloning again.

```bash
git checkout main
git pull
find . -name ".DS_Store" -print -delete
git add -A ; git commit -am "Update" ; git push
git checkout --orphan latest_branch
git add -A
git commit -am "Initial commit"
git branch -D main
git branch -m main
git push -f origin main
git branch --set-upstream-to=origin/main main
```

## Fix pull error different copy after resetting commit history

```bash
git pull --rebase
```

## Shell / Finder Commands

### Shows hidden files in Finder

With Finder press following key sequence

```bash
Cmd Shift . 
```

### Nuke .DS_Store

```bash
find . -name ".DS_Store" -print -delete
```
