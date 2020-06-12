Yum performs a number of steps when it downloads a package from a repository configured with "gpgcheck = 1" (the default).

1. After the first package from a repository is downloaded, a simple "is this package signed with a known gpgkey" call is done. If it is, nothing is done. If it isn't a warning is displayed to the user. This is purely informational.

2. Before the transaction starts yum checks that the package is signed with a known gpgkey (one already installed in the rpmdb), if it is the package is valid and no other steps are performed. If not then it continues to #3.

3. Yum downloads all the files given in the "gpgkey" data for the repository that the package comes from. Yum parses that, ignoring any keys already present in the rpmdb. If there are no new keys, yum will fail.

4. If there is a "gpgcakey" specified for the repository, then yum will download all the files given in the "gpgcakey" data. Yum parses that, ignoring any keys already present in that repositories gpg keyring. If there are no gpgcakeys installed after parsing the file, yum will fail. If there are new gpgcakeys, then if they are already imported as CA keys for another repo. they are automatically imported. If this is the first tiem we've seen this CA key the user is asked if he wants to install the key (unless -y is given). If he says no to any key, yum fails (although all imported keys stay in the repo. gpg keyring).

5. If there is at least one valid "gpgcakey", yum will try to download a "gpgkey".asc file. If that doesn't exists, yum moves on to step #6 as though there was no gpgcakey. If it does exist then the "gpgkey" is tested against the "gpgcakey" and if it passes it's added to the rpmdb, if it fails then yum fails (although all imported keys stay in the rpmdb).

6. If there are new gpgkeys, then the user is asked if he wants to install each key (unless -y is given). If he says no to any key, yum fails.

7. After installing any new keys, yum again checks the package signature against the gpgkeys in the rpmdb. If this fails, yum fails
