Always git stash - so with accidental git clean, can still recover

git pull specific branch
```
git pull 'remote_name' 'branch_name'
```

Push code to collaborative repo
```
git checkout -b feature-branch
git add .
git commit -m "Update"
git push --set-upstream origin feature-branch
```

Fix conflicts with main branch
```
git pull origin main
git checkout ignition-gps
git merge main # produces file conflicts with >>>> <<<<<
git push -u origin ignition-gps
```

Configure git on a new computer
```
# Add SSH key to VM so no need to ask for username and password ----
# Check if has files like id_rsa.pub
ls -al ~/.ssh

# Generate if none
ssh-keygen -t rsa -b 4096 -C "ncdejito@gmail.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
# for wsl, edit wsl_config with: https://github.com/Microsoft/WSL/issues/81#issuecomment-400597679
# chmod 400 ~/.ssh/id_rsa

# paste this to Github/Settings/SSH and GPG keys https://github.com/settings/keys
cat ~/.ssh/id_rsa.pub

# test connection if working
ssh -T git@github.com

# for each repo you push to, 
git remote set-url origin git@github.com:ncdejito/repo
```

revert back 1 commit
```
# go forward 1 commit
git checkout HEAD@{1}

# go back 1 commit, add --hard to discard current changes
git reset HEAD~1

# revert to a specific commit in github
# First, check out the commit you wish to go back to (get sha-1 from git log)
git reset --hard fe07c2fc093edb10ae6ec5c0abb43e5c3dd0f153

# Then do a forced update.
git push origin +fe07c2fc093edb10ae6ec5c0abb43e5c3dd0f153^:branch

# Push specific commit
git push origin fe07c2fc093edb10ae6ec5c0abb43e5c3dd0f153:branch
```
delete branch
```
git branch -D old-branch
```

rename master to main
```
git branch -M main
```

Delete git in a folder (if subfolder of repo is cloned from somewhere)
```
rm -rf .git
```
git_routines.sh
```
# list files changed for specific commit
git diff-tree --no-commit-id --name-only -r bd61ad98

# when experiencing conflicts, delete commit history in branch then force push
git reset --soft origin/master
git commit -m "Message"
git push -f

# force merge branch to master
git checkout seotweaks
git merge -s ours master
git checkout master
git merge seotweaks

# remove file from history
git rebase -it hashkeyajsdhfasjd~1
# change pick to edit
# remove token, make it empty string
git rebase --continue
```

Set origin to new repo
```
git remote set-url origin git://new.url.here
```

Add commit push in one command [git utils](https://github.com/ncdejito/config)
```
# https://simplernerd.com/git-alias-add-commit-push/
# can be seen in ~/.gitconfig
git config --global alias.acp '!f() { git add . && git commit -m "$@" && git push origin HEAD; }; f'

git acp "commit message"
```

Display image in readme
```
# in README.md
![](assets/proof.png)
```

For context switching, save current working dir state in a stash
```
# Store current working dir, including untracked
git stash -u

# retrieve latest stash, remove item from stash
git stash pop stash@{0}

# retrieve latest stash, dont remove item from stash
git stash apply stash@{0}
```

Restore accidental git clear
```
git fsck --unreachable | grep commit | cut -d ' ' -f3 | xargs git log --merges --no-walk --grep=WIP
```

Search commits
```
git log --grep="fix bug"
```

Work on multiple branches of a single codebase
```
git worktree add ../cool-app-feature-A feature/A  
# Does not support submodules
```

garbage collect, housekeeping
```
git gc
```
## Errors
#fix [[Version code with Git]] no anonymous write access
Source of error is VSCode CLI authentication
[instructions](https://stackoverflow.com/a/70035832)

#fix error: update_ref failed for ref 'refs/remotes/origin/main': cannot lock ref 'refs/remotes/origin/main': Unable to create '/.git/refs/remotes/origin/main.lock': Permission denied
* delete folder and re-clone repo

#fix error: submodule 'folder/path' has dirty index - delete folder, then git restore folder/path

always add `--recurse-submodules` when working with submodules (repo within the repo)
[Git - Submodules (git-scm.com)](https://git-scm.com/book/en/v2/Git-Tools-Submodules)

Git pull is stuck

git fsck && git gc --prune=now

(note) useful lfs (Large File Storage) commands: "git lfs status"; "git lfs ls-files", "git lfs env"; "git lfs track/untrack "file.ext"", "git lfs prune" (use "git config --global lfs.pruneverifyremotealways true" for making sure pruning deletes files still present on server), see also "git lfs help".

## Github alternatives

[The Git Rebase Handbook – A Definitive Guide to Rebasing (freecodecamp.org)](https://www.freecodecamp.org/news/git-rebase-handbook/)

[Git Squash Commits – Squashing the Last N Commits into One Commit (freecodecamp.org)](https://www.freecodecamp.org/news/git-squash-commits/)
Sourcehut - barebones
Gitlab - slow

Pro Git book
https://git-scm.com/book/en/v2

Conventions in git messages
https://www.conventionalcommits.org/en/v1.0.0/

Conventional comments
https://conventionalcomments.org/