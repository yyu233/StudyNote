## Git is automatically merging changes from a different branch to master ##

When you are editing files in your working directory, you are not editing "git" files (of any branch or master) at that point, you are just editing your local files, or "working directory" as it's called.

The "git" files (stuff that you have committed) are all in the .git directory. The layout matches your folders and this is where branches are also stored. Sidenote: it stores the actual files(compressed) unlike version control tools like svn that store the delta(difference)

So when you are editing a file you are not actually editing either master or branch, you are just editing the file. If you don't commit but then switch branches you will still have that file, and its changes will be visible even though you have 'switched' to the new branch. This is what usually surprises people initially.

The best advice here is to commit / ignore / discard all your changes before switching branches to avoid these issues. Also tools like gitx (Mac)m and gitg (Ubuntu) make these tasks easier for those whom like gui's and they also have good warnings about such issues.

[Reference](https://stackoverflow.com/questions/8111991/git-is-automatically-merging-changes-from-a-different-branch-to-master)
