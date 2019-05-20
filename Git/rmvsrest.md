``` git rm --cached ``` is used to remove a file from the index. In the case where the file is already in the repo, git rm --cached will remove the file from the index, leaving it in the working directory and a commit will now remove it from the repo as well. Basically, after the commit, you would have unversioned the file and kept a local copy.

``` git reset HEAD file ``` ( which by default is using the --mixed flag) is different in that in the case where the file is already in the repo, it replaces the index version of the file with the one from repo (HEAD), effectively unstaging the modifications to it.