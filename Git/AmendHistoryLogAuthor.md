```
git config user.name "New User"
git config user.email "newuser@gmail.com"

git log
git rebase -i 1f1357
# change the word 'pick' to 'edit', save and exit

git commit --amend --reset-author --no-edit
git rebase --continue

git push --force-with-lease
```
