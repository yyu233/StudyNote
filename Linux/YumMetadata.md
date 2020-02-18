* repomd.xml: Essentially an index that contains the location, checksums, and timestamp of the other XML metadata files listed below.
* repomd.xml.asc: This file is generated only if the repository creator has signed the repomd.xml file using GPG, as shown in the above example. yum will download and verify this signature if the user has the pygpgme package installed.
* primary.xml.gz: Contains detailed information about each package in the repository. You’ll find information like name, version, license, dependency information, timestamps, size, and more.
* filelists.xml.gz: Contains information about every file and directory in each package in the repository.
* other.xml.gz: Contains the changelog entries found in the RPM SPEC file for each package in the repository
