The asm keyword allows you to embed assembler instructions within C code. GCC provides two forms of inline asm statements. A basic asm statement is one with no operands (see Basic Asm), while an extended asm statement (see Extended Asm) includes one or more operands. The extended form is preferred for mixing C and assembly language within a function, but to include assembly language at top level you must use basic asm.

You can also use the asm keyword to override the assembler name for a C symbol, or to place a C variable in a specific register.
