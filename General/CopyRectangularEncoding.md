The copy rectangle encoding, for example, is very simple and efficient and can be used when the client already has the same pixel data elsewhere in its framebuffer. The server simply sends an X,Y coordinate giving the position  from which the client can copy the rectangle of pixel data. This means that operations such as dragging or scrolling a window, which involve substantial changes to the screen, may only require a few bytes. Most clients will support this encoding, since it is generally simple to implement and saves bandwidth.

A typical workstation desktop has large areas of solid colour and of text. Some of our most effective encodings take advantage of this by efficiently describing rectangles consisting of one majority (background) colour and 'sub-rectangles' of different colours. There are numerous other possible schemes.  We might use a JPEG encoding for still images or MPEG for efficient transmission of moving images. An encoding which uses some kind of caching of pixel data would be good for rendering text, where the same character is drawn in the same font multiple times. Subsequent occurrences of the same character would be encoded simply by reference to the first occurrence.