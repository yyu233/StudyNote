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

