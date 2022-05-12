[Ref](https://www.freedesktop.org/software/systemd/man/systemd.generator.html)

This takes advantage of the fact that not all connections between units are expressed inside the unit files. Wants and Requires dependencies can be expressed with symbolic link farms in *.wants/ and *.requires/ subdirectories. And those symbolic link farms encompass subdirectories of /run/systemd/ amongst other things.

In other words: Rather than write out a unit with WantedBy=local-fs.target and then have to explicitly invoke sytemctl enable to make the symbolic link (which is what enabling does), the generator short-circuits the process and makes the symbolic link itself. And it makes it in an ephemeral place, which systemctl enable normally would not, thereby preventing the symbolic link from continuing to exist after the next shutdown and confusing the next startup.
