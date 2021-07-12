The data in an archive is grouped into blocks, which are 512 bytes. Blocks are read and written in whole number multiples called records. The number of blocks in a record (i.e., the size of a record in units of 512 bytes) is called the blocking factor. The ‘--blocking-factor=512-size’ (‘-b 512-size’) option specifies the blocking factor of an archive. The default blocking factor is typically 20 (i.e., 10240 bytes), but can be specified at installation. To find out the blocking factor of an existing archive, use ‘tar --list --file=archive-name’. This may not work on some devices.

Records are separated by gaps, which waste space on the archive media. If you are archiving on magnetic tape, using a larger blocking factor (and therefore larger records) provides faster throughput and allows you to fit more data on a tape (because there are fewer gaps). If you are archiving on cartridge, a very large blocking factor (say 126 or more) greatly increases performance. A smaller blocking factor, on the other hand, may be useful when archiving small files, to avoid archiving lots of nulls as tar fills out the archive to the end of the record. In general, the ideal record size depends on the size of the inter-record gaps on the tape you are using, and the average size of the files you are archiving. See