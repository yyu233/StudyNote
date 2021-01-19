
SME provides the ability to mark individual pages of memory as encrypted using
the standard x86 page tables.  A page that is marked encrypted will be
automatically decrypted when read from DRAM and encrypted when written to
DRAM.  SME can therefore be used to protect the contents of DRAM from physical
attacks on the system.
