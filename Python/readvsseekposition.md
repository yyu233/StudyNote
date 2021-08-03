seek is always in terms of bytes,* not characters, even for files opened in text mode.

There's no way it could work remotely efficiently otherwise—the millionth character in a UTF-8 text file could be at byte 1,000,000 or at byte 2,739,184, and the only way to find out is to go back to the start and encode 999,999 characters.**

But read is only reading bytes if you're in binary mode; in text mode, those bytes are decoded to Unicode strings on the fly. (Since you're reading the file sequentially, this isn't usually a performance issue—but when it is, you've always got binary mode.)

If you have a known position you want to be able to return to, you can "mark" it by calling tell and then seek back to it later, but otherwise, seeking isn't very useful in text files, except to the start or end of the file of course.
