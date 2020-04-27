The find -L trick quoted by solo from commandlinefu looks nice and hacky, but it has one very dangerous pitfall: All the symlinks are followed. Consider directory with the contents presented below:

```
$ ls -l
total 0
lrwxrwxrwx 1 michal users  6 May 15 08:12 link_1 -> nonexistent1
lrwxrwxrwx 1 michal users  6 May 15 08:13 link_2 -> nonexistent2
lrwxrwxrwx 1 michal users  6 May 15 08:13 link_3 -> nonexistent3
lrwxrwxrwx 1 michal users  6 May 15 08:13 link_4 -> nonexistent4
lrwxrwxrwx 1 michal users 11 May 15 08:20 link_out -> /usr/share/
```

If you run find -L . -type l in that directory, all /usr/share/ would be searched as well (and that can take really long)1. For a find command that is "immune to outgoing links", don't use -L

*Note:
So need to consider how deep any search goes. 
