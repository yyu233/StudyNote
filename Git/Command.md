Reset last commit: **git reset --hard HEAD^**  

Track upstream: **git branch -u remote/branch**   

Untrack upstream: **git branch --unset-upstream**  

Check tracking info for all branches: **git branch -vv**

Delete branch: **git branch --delete \<branch>**   

Rename local branch (on this branch: **git branch -m \<newname>**  

Rename local brach (on different branch): **git branch -m <\oldname> \<newname>**  

Replace the old remote branch name with the new name: **git push origin: \<oldname> \<newname>**    

Push to remote and track: **git push -u origin remotebranch**   

Remove file from index before commit: **git rm --cached <\filename>**   

Pull and avoid merging:  **git pull --rebase /<remote/branch>**    

Sqush local commit into one commit: **git rebase -i \<hash>**   

Undo git checkout: **git checkout -**   

Clean git untracked file and directory: **git clean -f -d**   

Save uncommitted changes (both staged and unstaged): **git stash**   

Save uncommitted changes (include untracked files such as new files): **git stash -u**   

Reapplying stashed changes (removes changes from stash): **git stash pop**    

Reapplying stashed changes (keep changes in stash for applying to multiple branches):  **git stash apply**    

Display all stashed changes: **git stash list**    

Annotate stashed changes with description: **git stash save \<description>**    

Choose which stash to re-apply: **git stash pop stash@{#}**   

Display a summary of stashed change: **git stash show** 

Display a full diff of stash: **git stash show -p**   

Create a branch from stash when the changes on branch diverge from the changes in your stash: **git stash branch \<name> stash@{#}**     

Delete a stashed change: **git stash drop stash@{#}**    

Delete all stashe changes: **git stash clear**    





