With open, you have accepted the default buffering setting (by not providing a buffering argument), so you're getting a buffered file object. This buffer is separate from any OS-level buffering.

With os.open, there is no file object and no file-object-level buffering.

