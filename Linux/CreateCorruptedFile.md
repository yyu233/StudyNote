Write some zeroes into the middle of the file. Use dd with conv=notrunc. This writes a single byte (block-size=1 count=1):
```
dd if=/dev/zero of=file_to_fuzz.zip bs=1 count=1 seek=N conv=notrunc
```
Using /dev/urandom as a source is also an option.

Alternatively, punch multiple-of-4k holes with fallocate --punch-hole. You could even fallocate --collapse-range to cut out a page without leaving a zero-filled hole. (This will change the file size).

A download resumed at the wrong place would match the --collapse-range scenario. An incomplete torrent will match the punch-hole scenario. (Sparse file or pre-allocated extents, either read as zero anywhere that hasn't been written yet.)

Bad RAM (in the system you downloaded the file from) can cause corruption, and optical drives can also corrupt files (their ECC isn't always strong enough to recover perfectly from scratches or fading of the dye).

DVD sectors (ECC blocks) are 2048B, but single byte or even single-bit errors can happen. Some drives will probably give you the bad uncorrectable data instead of a read-error for the sector, especially if you read in raw mode, or w/e it's called
