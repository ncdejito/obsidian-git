Configure git on a new computer
```
# Git 2FA 4b2302f817077a4dbc220fdd3329632a7455271a

# Add SSH key to VM so no need to ask for username and password ----
# Check if has files like id_rsa.pub
ls -al ~/.ssh

# Generate if none
ssh-keygen -t rsa -b 4096 -C "ncdejito@gmail.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
# for wsl, edit wsl_config with: https://github.com/Microsoft/WSL/issues/81#issuecomment-400597679
# chmod 400 ~/.ssh/id_rsa

# paste this to Github/Settings/SSH and GPG keys
cat ~/.ssh/id_rsa.pub

# test connection if working
ssh -T git@github.com
```

revert back 1 commit
```
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
git branch –delete old-branch
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

Add commit push in one command
```
# https://simplernerd.com/git-alias-add-commit-push/
git config --global alias.acp '!f() { git add . && git commit -m "$@" && git push origin HEAD; }; f'

git acp "commit message"
```