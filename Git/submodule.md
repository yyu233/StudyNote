## Submodules - repos inside other repos ## 
Git allows you to include other Git repositories called submodules into a repository. This allows you to track changes in several repositories via a central one. Submodules are Git repositories nested inside a parent Git repository at a specific path in the parent repository’s working directory. A submodule can be located anywhere in a parent Git repository’s working directory and is configured via a .gitmodules file located at the root of the parent repository. This file contains which paths are submodules and what URL should be used when cloning and fetching for that submodule. Submodule support includes support for adding, updating, synchronizing, and cloning submodules.

```
git clone --recursive [URL]                             # clone a repo including its submodules
git submodule update --init --recursive                 # if clone a repo and want to load it's submodules including nested submodules
git submodule update --init --recursive -j <#jobs>      # Load mutiple submodules parrallel
git pull --recursive-submodules                         # pull all changes in the repo including changes in submodules
git submodule update --remote                           # pull all changes for the submodules
git submodule foreach '<git command>' --recursive       # executing command on every submodule including nested submodules
git submodule add -b "<branch>" [URL]                   # add a new submodule to existing git and defines master branch to be tracked
git submodule init                                      # initialize submodule configuration 

```

## Commit with submodules ## 
The relevant state for the submodules are defined by the main repository. If you commit in your main repository, the state of the submodule is also defined by this commit.

The git submodule update command sets the Git repository of the submodule to that particular commit. The submodule repository tracks its own content which is nested into the main repository. The main repository refers to a commit of the nested submodule repository.

Use the git submodule update command to set the submodules to the commit specified by the main repository. This means that if you pull in new changes into the submodules, you need to create a new commit in your main repository in order to track the updates of the nested submodules.
