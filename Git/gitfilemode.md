32-bit mode, split into (high to low bits)

    4-bit object type
      valid values in binary are 1000 (regular file), 1010 (symbolic link)
      and 1110 (gitlink)

    3-bit unused

    9-bit unix permission. Only 0755 and 0644 are valid for regular files.
    Symbolic links and gitlinks have value 0 in this field.
