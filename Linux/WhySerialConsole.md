High density racks of computers

    Clusters of personal computers can outperform mainframe computers and form competitive supercomputers for some applications. See the Cluster-HOWTO for more information on clustering.

    These clusters are typically assembled into 19 inch telecommunications equipment racks and the system unit of each computer is typically one rack unit (or 1.75 inches) tall. It is not desirable to put a keyboard and monitor on each computer, as a small cathode ray tube monitor would consume the space used by sixteen rack units.

    A first glance it seems that a monitor and keyboard switch is the best solution. However the VGA signal to the monitor is small, so even with the switch the monitor cannot be placed very far away from the rack of computers.

    It is desirable to allow the consoles to be monitored in the operators' room of the computer center, rather than in the very expensive space of the machine room. Although monitor switches with remote control and fiber optical extensions are available, this solution can be expensive.

    A standard RS-232 cable can be 15 meters in length. Longer distances are easily possible. The cabling is cheap. Terminal servers can be used to allow one terminal to access up to 90 serial consoles.
Recording console messages

    This is useful in two very different cases.

    Kernel programmers are often faced with a kernel error message that is displayed a split second before the computer reboots. A serial console can be used to record that message. Another Linux machine can be used as the serial terminal.

    Some secure installations require all security events to be unalterably logged. One way to meet this requirement is to print all console messages. Connecting the serial console to a serial printer can achieve this
