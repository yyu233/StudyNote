NEON instructions
The NEON instructions provide data processing and load/store operations only, and are integrated into the ARM and Thumb instruction sets. Standard ARM and Thumb instructions manage all program flow control.

The encodings for NEON instructions correspond to coprocessor operations affecting coprocessors 10 and 11, the same as VFP instructions. NEON and VFP instructions are also grouped together alphabetically because all mnemonics begin with a capital V.

Most instructions can operate on different data types, specified in the instruction encoding. Software indicates the size required by appending a suffix to the instruction mnemonic. The number of elements operated on is indicated by the specified register size. For example, VADD.I16 q0, q1, q2 indicates an operation on 16-bit integer elements stored in 128-bit Q registers. This means that the operation is on eight 16-bit lanes in parallel.

Some instructions can have different size input and output registers. For example, VMULL.S16 Q0, D2, D3 multiplies four 16-bit lanes in parallel, producing four 32-bit products in a 128-bit destination vector.

To improve code density and performance, the NEON instruction set includes structured load and store instructions that can load or store single or multiple values from or to single or multiple lanes in a vector register. It also includes instructions that transfer complete data structures between several vector registers and memory, with interleaving and de-interleaving.
