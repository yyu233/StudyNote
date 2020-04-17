When moving data across filesystems, neither is more efficient - they're about the same. the cp,verify,rm strategy is safer because it is easier to recover from an unexpected error - e.g. the mv or cp failing partway through due to disk full error or (if the destination fs is a network share) the network going down, etc. With cp you still have your complete original data in its original directory structure. With mv you have some of your data in the original dir, some in the target dir, and re-merging them may be difficult (esp. if the target dir contains other data).

if cp fails before completion due to error, once you have resolved the error you can complete the cp from where it left off by using rsync. In fact, you can use rsync instead of cp right from the start.

Technically, mv is not atomic when the source and destination are on different filesystems, it is actually cp + unlink(). So at first mv will copy the file and then call unlink() to remove the file from the directory's list of entries.

So in this case, AFAIU whether you cp and then rm (unlink()) or use mv directly is totally your personal preference.

Whereas while mv -ing within the same filesystem, you should use mv as its atomic within the same filesystem (calls rename()) so less overhead.
