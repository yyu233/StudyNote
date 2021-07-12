/dev/hdc
is the third IDE hard drive - Secondary Master.

/dev/sr0
is the first SCSI CD-ROM device in the system. This may be misleading as SCSI and SATA are interchangeable in Linux terminology. There is also SCSI emulation of ATAPI devices in some Unix systems (in FreeBSD it's called ATAPICAM) which makes ATAPI CD-ROM devices appear to be SCSI. Some older software is written purely to interface with SCSI peripherals and can't work with ATAPI ones, so this emulation layer can be quite useful.

/dev/cdrom
And yes, that is a symlink to one of the above - either done manually with ln or through the udev configuration.
