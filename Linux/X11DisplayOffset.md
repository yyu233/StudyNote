X11DisplayOffset does not refer to an offset within the geometry of the display - it relates to the identification of which display clients started over the SSH connection should use in order not to interfere with local displays. From man sshd_config:

 X11DisplayOffset
         Specifies the first display number available for sshd(8)'s X11
         forwarding.  This prevents sshd from interfering with real X11
         servers.  The default is 10.
The architecture of X Windows allows for an X server to manage multiple displays. Typically on a standalone workstation with a single local user, you only have to deal with a single display - usually numbered 0 and often referred to as :0, for example in environment variable assignments like DISPLAY=:0. But on servers that may be running several X sessions (users remoting in via VNC for example, or separate X sessions on different virtual terminals) there may be multiple displays, labelled :1, :2, and so on.

When X11 forwarding over SSH is added to the mix, that adds a requirement for additional unique display numbers (so that X clients tunneled over the SSH connection get directed to the correct remote display server). In order to avoid conflicts with local displays, an offset is added to the display numbering scheme so that the remote displays are numbered :10, :11, :12, ...
