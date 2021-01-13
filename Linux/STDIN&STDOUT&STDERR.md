```

Standard input and standard output are not commands.

Imagine commands as machines in a factory with an assembly line. Most machines are designed to have one conveyor belt to feed data in and one conveyor belt to feed data out; they are the standard input and the standard output respectively. The standard error is an opening on the side of the machine where it can eject rejects.

+-------+     +------------------+       +------------------+     +------+
| input |     |    machine A     |       |    machine B     |     |output|
| reser ­­­|=====|<stdin     stdout>|=======|<stdin     stdout>|=====|bucket|
| ‑voir |  →  |      stderr      |   →   |      stderr      |  →  |      |
+-------+     +------------------+       +------------------+     +------+
                      ||                          ||

The diagram above shows a conveyor belt that goes through two machines. The data comes from the input reservoir on the left, is fed to machine A, then the output is conveyed further to machine B (for which it is input), and machine B's output is deposited in the output bucket on the right.

In unix terms, this is called a pipeline. The metaphor is that of plumbing: a pipe connects machine A to machine B. The shell syntax for the pipeline above is

<input-file.txt commandA | commandB >output-file.txt

The < redirection symbol tells the shell to connect commandA's standard input to the file input-file.txt before launching commandA. (You can put the redirection before or after the command name.) The > redirection symbol tells the shell to connect commandB's standard output to output-file.txt. The pipe ("|") symbol in the middle tells the shell to connect commandA's standard output to commandB's standard input before launching them.

```
