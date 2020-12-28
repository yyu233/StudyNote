```
The RFC defines the algorithm as

inhibit the sending of new TCP segments when new outgoing data arrives from the user if any previously transmitted data on the connection remains unacknowledged.

Where MSS is the maximum segment size, the largest segment that can be sent on this connection, and the window size is the currently acceptable window of unacknowledged data, this can be written in pseudocode as[citation needed]

if there is new data to send then
    if the window size ≥ MSS and available data is ≥ MSS then
        send complete MSS segment now
    else
        if there is unconfirmed data still in the pipe then
            enqueue data in the buffer until an acknowledge is received
        else
            send data immediately
        end if
    end if
end if

```
