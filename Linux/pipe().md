pipe() creates a pipe, a unidirectional data channel that can be
       used for interprocess communication.  The array pipefd is used to
       return two file descriptors referring to the ends of the pipe.
       pipefd[0] refers to the read end of the pipe.  pipefd[1] refers
       to the write end of the pipe.  Data written to the write end of
       the pipe is buffered by the kernel until it is read from the read
       end of the pipe. 
