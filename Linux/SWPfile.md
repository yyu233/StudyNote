## SWP file ##
SWP stands for SWaP file. SWP files are located on a computer’s hard drive, used by the virtual memory component of the computer to increase available memory. SWP files contain any data that has been “swapped” from the computer’s memory to the hard drive. SWP files are also referred to as “Paging” files as they store “Pages” of the computer’s memory.   

.swp files are nothing but a kind of lock file which you editor, generally vim, creates to indicate that file is being edited. This way if you open the file in another vim instance of if someone in the network did that, they'll see a warning that the file is being edited.
You need not to delete them manually. You editor will remove the swap file once you close the file in your editor.  

If there is a crash (power failure, OS crash, etc.), then you can recover your changes using this swap-file. 
