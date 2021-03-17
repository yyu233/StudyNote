OpenMP is a way to program on shared memory devices. This means that the parallelism occurs where every parallel thread has access to all of your data.

You can think of it as: parallelism can happen during execution of a specific for loop by splitting up the loop among the different threads.

MPI is a way to program on distributed memory devices. This means that the parallelism occurs where every parallel process is working in its own memory space in isolation from the others.

You can think of it as: every bit of code you've written is executed independently by every process. The parallelism occurs because you tell each process exactly which part of the global problem they should be working on based entirely on their process ID.


MPI stands for Message Passing Interface. It is a set of API declarations on message passing (such as send, receive, broadcast, etc.), and what behavior should be expected from the implementations.

The idea of "message passing" is rather abstract. It could mean passing message between local processes or processes distributed across networked hosts, etc. Modern implementations try very hard to be versatile and abstract away the multiple underlying mechanisms (shared memory access, network IO, etc.).

OpenMP is an API which is all about making it (presumably) easier to write shared-memory multi-processing programs. There is no notion of passing messages around. Instead, with a set of standard functions and compiler directives, you write programs that execute local threads in parallel, and you control the behavior of those threads (what resource they should have access to, how they are synchronized, etc.). OpenMP requires the support of the compiler, so you can also look at it as an extension of the supported languages.

|MPI| OpenMP|
|----|-----|
| Available from different vendor and can be compiled in desired platform with desired compiler. One can use any of MPI API i.e MPICH, OpenMPI or other|OpenMP are hooked with compiler so with gnu compiler and with Intel compiler one have specific implementation. User is at liberty with changing compiler but not with openmp implementation|
|MPI support C,C++ and FORTRAN|OpenMP support C,C++ and FORTRAN|
|OpenMPI one of  API for MPI is providing provisional support for Java|Few projects try to replicate openmp for Java|
| MPI target both distributed as well shared memory system|OpenMP target only shared memory system|
|Based on both process and thread based approach .(Earlier it was mainly process based parallelism but now with MPI 2 and 3 thread based parallelism is there too. Usually a process can contain more than 1 thread and call MPI subroutine as desired|Only thread based parallelism|
|Overhead for creating process is one time|Depending on implementation threads can be created and joined for particular task which add overhead|
|There are overheads associated with transferring message from one process to another|No such overheads, as thread can share variables|
|Process in MPI  has private variable only, no shared variable|In OpenMP , threads have both private as well shared variable|
|Data racing is not there if not using any thread in process| Data racing is inherent in OpenMP model|
|Compilation of MPI program require. 1. Adding header file : #include "mpi.h" 2. compiler as:(in linux ) mpic++  mpi.cxx -o mpiExe.  (User need to set environment variable PATH and LD_LIBRARY_PATH to MPI as OpenMPI installed folder or binaries) (For Linux)| Need to add  omp.h and then can directly compile code with -fopenmp in Linux environment   g++ -fopenmp openmp.cxx -o openmpExe| 
|Running MPI program   1. User need to make sure that bin and library folder from MPI installation are included in environmental variable PATH and LD_LIBRARY_PATH. 2. For running executable from command line ,user need to supply following command and specify number of processor as in example below it is four .    mpirun -np 4 mpiExe| User can launch executable openmpExe in normal way.  ./openmpExe|


