At some point in your Git journey, you may accidentally lose a commit. Generally, this happens because you force-delete a branch that had work on it, and it turns out you wanted the branch after all; or you hard-reset a branch, thus abandoning commits that you wanted something from. Assuming this happens, how can you get your commits back?    

Often, the quickest way is to use a tool called ``` git reflog ```. As you’re working, Git silently records what your HEAD is every time you change it. Each time you commit or change branches, the reflog is updated. The reflog is also updated by the git update-ref command, which is another reason to use it instead of just writing the SHA-1 value to your ref files.    

Find the lost commit by using ``` git reflog ```, and then checkout a new branch to attach to this lost commit.  reflog data is kept in 
``` .git/logs/ ```. If ``` .git/logs/ ``` gets cleaned up and you can't find lost commit by ``` git reflog ```. One way is to use the git fsck utility, which checks your database for integrity. If you run it with the --full option, it shows you all objects that aren’t pointed to by another object
