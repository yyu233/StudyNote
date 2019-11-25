``` echo "" > file ``` will release memory. ``` rm -f file ``` may not release memory if application is using the file.
