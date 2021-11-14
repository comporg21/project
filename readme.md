computer organization 21 project description
============================================

you need to write a program that

* takes as an argument a file that contains forth like code (description below)
* translates the content of the file to x86_64 or aarch64 assembly, writes in another file.
* calls programs 'as' and 'ld' to build and link the resulting executable.

you don't write an interpreter, you write a compiler (translator).
you can use any language for writing the project.

supported syntax
================

the input language is a minimal forth subset.

the source file processed by your program may contain separated by 'whitespace' or 'EOL' symbols words.

words can be:
* decimal numbers
* predefined commands

for example, the input file may look like this:

------------------------
40 2 
+
.
------------------------

or like this

------------------------
-42
0 swap -
.
------------------------


when you encounter '.' lexem in the program, you should generate a piece of assembly language program that outputs to stdout the number on the top of the stack.

operations:

+ - addition. the two operands should be located on top of the stack. code should be generated to add them and replace two operands in the stack by one result of the addition on the top of the stack.

same with operations -, *, /, %.

our forth subset also supports:

swap - using temporary location for swapping two stack locations will cause a decrease in grade.
dup
drop
over
nip

