 The epoll API performs a similar task to poll(2): monitoring
       multiple file descriptors to see if I/O is possible on any of
       them.  The epoll API can be used either as an edge-triggered or a
       level-triggered interface and scales well to large numbers of
       watched file descriptors.

       The central concept of the epoll API is the epoll instance, an
       in-kernel data structure which, from a user-space perspective,
       can be considered as a container for two lists:

       • The interest list (sometimes also called the epoll set): the
         set of file descriptors that the process has registered an
         interest in monitoring.

       • The ready list: the set of file descriptors that are "ready"
         for I/O.  The ready list is a subset of (or, more precisely, a
         set of references to) the file descriptors in the interest
         list.  The ready list is dynamically populated by the kernel as
         a result of I/O activity on those file descriptors.
