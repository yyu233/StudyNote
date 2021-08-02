In a single sentence, we can say that shutil is consisting of high-level Python specific functions. shutil is on top of Python’s os module. Thus, we can use the shutil module for high-level operations on files.

1. OS module might fail to move a file if the source and destination path is on different file systems or drive.
But shutil.move will not fail in this kind of cases.
2. shutil.move checks if the source and destination path are on the same file system or not. But os.rename does not check, thus it fails sometimes.
3. After checking the source and destination path, if it is found that they are not in the same file system, shutil.move will copy the file first to the destination. Then it will delete the file from the source file. Thus we can say shutil.move is a smarter method to move a file in Python when the source and destination path are not on the same drive or file system.
4. shutil.move works on high-level functions, while os.rename works on lower-level functions.
