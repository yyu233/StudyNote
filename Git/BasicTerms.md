## Basic Terms ##

* **Working Directory**     
* **Index**    
* **Local Repo**     
* **Remote Repo**

1. the workspace is the directory tree of (source) files that you see and edit.

2. The index is a single, large, binary file in <baseOfRepo>/.git/index, which lists all files in the current branch, their sha1 checksums, time stamps and the file name -- it is not another directory with a copy of files in it.

3. The local repository is a hidden directory (.git) including an objects directory containing all versions of every file in the repo (local branches and copies of remote branches) as a compressed "blob" file

[Good Read](https://hackernoon.com/understanding-git-index-4821a0765cf)
