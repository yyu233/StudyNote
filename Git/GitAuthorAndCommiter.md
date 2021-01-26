```
Each commit on GitHub is associated with three people: its author, its committer, and its pusher.

You author a commit when you make changes to files in a repository. You commit a commit when you apply the changes to the repository’s history. You push a commit when you send those changes from the local repository on your computer to the remote repository on GitHub.

Often, a commit will be authored, committed, and pushed by the same person… but not always! Continue reading to learn how these roles are different and what to do if any one of them looks wrong on GitHub.

Author

You author a commit when you make changes to files in a repository. Usually, that means writing code! An author is identified by both a name and an email address, like Laura Coursen <lecoursen@github.com>. 

If you’re working locally, you can tell Git who authored a set of changes by using the --author flag with git commit. If multiple people contributed to a set of changes, you can add one or more Co-authored-by trailers to the commit’s message to give them all credit. For more information, see “Creating a commit with multiple authors 46.” If you don’t specify any authors, the user.name and user.email from your local Git configuration will be used by default.

If you’re working on GitHub and haven’t enabled Keep my email address private , we’ll use the name in your profile settings 56 and your primary email address 56 as author information by default, but you can choose to use any other verified email address in your GitHub account each time you make a change. If you do have Keep my email address private enabled, the private email address provided by GitHub will be used instead. For more information, see “Setting your commit email address on GitHub 108.”

Whether you work locally or on GitHub, we use the email address(es) from this author information to associate GitHub accounts with commits in most places on our site, including contributions graphs and the commits list:

```
