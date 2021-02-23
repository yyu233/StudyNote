yumdownloader [options] package1 [package2...] http://linux.die.net/man/1/yumdownloader This seems to download the packages and their primary dependencies. What it does not do is download the dependencies of the dependencies. It Only downloads the top level dependencies of the package.

repotrack [options] package1 [package2...] http://man7.org/linux/man-pages/man1/repotrack.1.html This downloads the packages and all of their dependencies along with the sub-level dependencies that are needed.
