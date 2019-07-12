If the file has any sort of buffering behind it it and you don't call close then you could potentially lose data.
If the OS has limited resources (e.g. number of open files) then by not closing files you are wasting system resources.
Using a descriptor once the file is closed is pointless at best, massive bug at worst (a bit like using memory after it has been freed)
