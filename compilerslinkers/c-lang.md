# Compiling and Linking in C

**Source program** is a sequence of bits, organized in 8-bit chunks called **bytes**

Modern systems represent text characters in ASCII or UTF-8

Sample Hello World program: ![](/assets/compile-c-1.png)Compilation system![](/assets/compilers-1)GCC compiler reads source and translates into executable object file, performed over four phases:

* Preprocessing - preprocessor \(`cpp`\) modifies the original C program according to directives \(\#\), resulting in another C program ending with `.i` suffix.
* Compilation - compiler \(`cc1`\) translates text file `hello.i` into text file `hello.s` which contains assembly language program. Compilers generate the same assembly for a specific system, no matter the source language.
* Assembly - assembler \(`as`\) translates `hello.s` into machine language instructions, packages them in form known as relocatable object program,  and stores result in `hello.o`
* Linking -  the linker \(`ld`\) handles merging external library components to the object file. Result is `hello` file which is an executable object file.



