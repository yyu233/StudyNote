Scheduling doesn't matter much at all. If you consider piping an hour long job, the pipe remains open continuously from when the first program is started until it finishes. The second program runs exactly the same time as the first one and both finish at the same time (in general)..

In other words, ps does not get the output then send it to grep - the two are run at the same time, and the output of one is entered to the second in real time. It doesn't wait for the first program to finish, collect an hour of data, then send it all to the second in one go.

Though in practice there's some level of buffering (a few hundred chars) especially when multiple pipes are involved. But for the most part, think of them both being run at the same time and talking directly to each other.

