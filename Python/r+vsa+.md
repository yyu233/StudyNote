r+ : - Open for reading and writing. The stream is positioned at the beginning of the file.

a+ : - Open for reading and writing. The file is created if it does not exist. The stream is positioned at the end of the file. Subse- quent writes to the file will always end up at the then current end of file, irrespective of any intervening fseek(3) or similar.
