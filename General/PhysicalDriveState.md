## Physical Drive State ##

**Unconfigured Good** :  A drive accessible to the RAID controller but not configured as a part of a virtual drive or as a hot spare.   
**Hot Spare**: a drive which is configuted as a hot spare  
**Online**: a drive that can be accessed by the RAID controller and will be part of the virtual drive.  
**Rebuild**: a drive to which data is being written to restore full redundancy for a virtual drive.   
**Failed** : a drive that was originally configtured as Online or Hot Spare, but on which the firmware detects an unrecoverable error.  
**Unconfigured bad**: a drive on which the firmware detects an unrecoverable error. The drive was Unconfigured Good or the drive could not be initialized.  
**Missing**: a drive that was Online, but which has been removed from its location.   
**Offline**: a drive that is part of a virtual drive but which has invalid data.    
**None**: a drive with an unsupported flag set.  
