The Event class object provides a simple mechanism which is used for communication between threads where one thread signals an event while the other threads wait for it. So, when one thread which is intended to produce the signal produces it, then the waiting thread gets activated.

An internal flag is used by the event object known as the event flag which can be set as true using the set() method and it can be reset to false using the clear() method.

The wait() method blocks a thread until the event flag for which it is waiting is set true by any other thread..
