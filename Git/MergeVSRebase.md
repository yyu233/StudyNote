## Merge vs Rebase ##

Merge is fast forward record move, while rebase is history rewritting.    
Merge does not change the existing branch. This avoids the potential pitfalls of rebasing. If master is very active, the history of your feature branch can be easily polluted. It may be hard for other developers to understand.    
Rebase will create a linear project history. Rebase doesn't create an extra commit message. It loses the context provided by a merge commit.     
Interactive rebasing with option ``` -i  ``` allows user to manually merge commits. This does not work on a branch where there are other developers also work on.  Merge does not have this ability.   
Golden rule of rebasing is not rebase on public branch. It moves the master onto the head of your branch, but everyone else is working on the original head of master. 

