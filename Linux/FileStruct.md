Different process will be allocated different file struct for a file. File struct maintains File Status Flag(f_flags), (f_pos) and (f_count).

Whenever a file descriptor referenced a same file struc, f_count will increment. Only when f_count becomes 0, close() will release the resource. 
