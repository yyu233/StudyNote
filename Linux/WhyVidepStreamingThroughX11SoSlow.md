The X11 protocol was never meant to handle graphically (in terms of bitmaps/textures) intensive operations. Back in the day when X11 was first designed computer graphics were a lot simpler than they are today.

Basically X11 doesn't send the screen to your computer, but it sends the display-instructions so the X-server on your local computer can re-create the screen on your local system. And this needs to be done on each change/refresh of the display.
So your computer receives a stream of instructions like "draw line in this color from coordinates x,y to (xx,yy), draw rectangle W pixels wide, H pixels high with upper-left corner at (x,y), etc."
The local client isn't really aware what needs to be updated and the remote system has very little information on what the client actually needs, so basically the server must send a lot of redundant information that the client may or may not need.
This is very efficient if the display to be rendered consists of a limited number of simple graphical shapes and only a low refresh frequency (no animations and such) is needed. Which was the case back in the days when X11 was first developed.

But modern GUI's have a lot of eye-candy and much of that needs to be send from the remote system to your client in the form of bitmaps/textures/fonts which take quite a lot of bandwidth. And all sorts of eye-candy includes animated effects requiring frequent updates. And the displays keep getting bigger too, twice as wide/high is 4x the number of pixels.

Of course, over time, enhancements to the X11 protocol were made to optimize this as much as possible, but the basic underlying design is, in essence, simply not well suited to the demands of the kind of GUI's people nowadays expect.

Other protocols (like RDP and VNC) are more designed to let the remote system do all the hard work and let that system decide which updates to send to the client (as compressed bitmaps) as efficiently as possible. Often that turns out to be more efficient for modern GUI's.

Neither method is perfect and can deal with every situation equally well. There is no such thing as a single display-protocol that can do well under every conceivable use-case.
So in most cases you just try all protocols that are supported between your local client and the remote server and use the one that gives the best results. And in some cases there is no choice and you just have to make do with whatever is available.

Most protocols do allow some performance tuning, but many of these settings are server-side only and not available to the average user. (And configuring them properly is a bit of an arcane art. A lot of sys-admins won't be willing to mess with that.)

In most cases the easiest way to improve performance (sometimes quite dramatically) is by switching to a more simple desktop environment with less eye-candy and forego the use of background images.

