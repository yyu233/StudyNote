This is the way passwords are stored on modern Windows systems, and can be obtained by dumping the SAM database, or using Mimikatz. They are also stored on domain controllers in the NTDS file. These are the hashes you can use to pass-the-hash.
Usually people call this the NTLM hash (or just NTLM), which is misleading, as Microsoft refers to this as the NTHash (at least in some places).
