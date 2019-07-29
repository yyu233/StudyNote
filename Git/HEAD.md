Usually the HEAD file is a symbolic reference to the branch you’re currently on. By symbolic reference, we mean that unlike a normal reference, it contains a pointer to another reference.

However in some rare cases the HEAD file may contain the SHA-1 value of a git object. This happens when you checkout a tag, commit, or remote branch, which puts your repository in "detached HEAD" state.

If you look at the file, you’ll normally see something like this:
```
$ cat .git/HEAD
ref: refs/heads/master
```
If you run git checkout test, Git updates the file to look like this:
```
$ cat .git/HEAD
ref: refs/heads/test
```
