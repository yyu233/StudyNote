A pseudo TTY (or "PTY") is a pair of devices — a slave and a master — that provide a special sort of communication channel. The slave device behaves much like the device representing the VT100 or ADM-3A "dumb terminal" that we all have on our desks ... or that we might have had a few decades ago. It can read and write text as though it were a physical terminal, it can enable or disable echo of typed characters, etc. The master acts more like the person sitting in front of that dumb terminal. Writing to the master is exactly like typing on a terminal. If echo is enabled, then everything written can immediately be read back, and writing a backspace effectively causes the previous character typed to be forgotten. Modern computers typically have very few, if any, physical terminals, but potentially lots of PTYs to support text-based interfaces as provided by terminal emulators (such as xterm or gnome-terminal) and remote access interfaces like SSH.