 * The git checkout command can be used in a commit, or file level scope. A file level checkout will change the file's contents to those of the specific commit.  
 * A revert is an operation that takes a specified commit and creates a new commit which inverses the specified commit. git revert can only be run at a commit level scope and has no file level functionality.   
 * A reset is an operation that takes a specified commit and resets the "three trees" to match the state of the repository at that specified commit. A reset can be invoked in three different modes which correspond to the three trees. 
 
 |Command|	Scope	|Common use cases|
 |--------|---|------|
|git reset	|Commit-level|	Discard commits in a private branch or throw away uncommited changes|
|git reset	|File-level	|Unstage a file|
|git checkout	|Commit-level	|Switch between branches or inspect old snapshots|
|git checkout	|File-level	|Discard changes in the working directory|
|git revert|	Commit-level	|Undo commits in a public branch|
|git revert	|File-level|	(N/A)|
