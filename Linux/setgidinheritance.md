The setuid and setgid flags, when set on a directory, have an entirely different meaning.

Setting the setgid permission on a directory (chmod g+s) causes new files and subdirectories created within it to inherit its group ID, rather than the primary group ID of the user who created the file (the owner ID is never affected, only the group ID). Newly created subdirectories inherit the setgid bit.

Thus, this enables a shared workspace for a group without the inconvenience of requiring group members to explicitly change their current group before creating new files or directories. Note that setting the setgid permission on a directory only affects the group ID of new files and subdirectories created after the setgid bit is set, and is not applied to existing entities. Setting the setgid bit on existing subdirectories must be done manually, with a command such as the following:
