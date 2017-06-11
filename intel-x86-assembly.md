# Intel x86 Assembly

## Assembly Basics

Two main forms of assembly syntax: 

* `AT&T` 
  * Used by GNU Assembler
  * Contained in GCC compiler
  * Often used by Linux Devs
* `Intel`
  * Netwide Assembler \(NASM\)
  * Used by many Windows assemblers and debuggers

### Styles of format:

The source and destination operands are reversed, and different symbols are used to mark the beginning of a comment:

NASM Format:

```
CMD <dest>, <source> <;comment>
```

AT&T Format:

```
CMD <source>, <dest> <#comment>
```

AT&T format uses a % before registers; NASM does not

AT&T format uses a $ before literal values; NASM does not

AT&T handles memory references differently than NASM.

## Commands

| NASM Syntax | NASM Example | AT&T Example |
| :--- | :--- | :--- |
| mov &lt;dest&gt;, &lt;source&gt; | mov eax, 51h ;comment | movl $51h, %eax \#comment |



## Assembly File Structure

• Broken into following sections

	• .model - indicates the size of the .data and .text sections.

	• .stack - marks the beginning of the stack section and indicates the size of the stack in bytes.

	• .data - marks the beginning of the data sections and defines the variable, both initialized and uninitialized

	\* .text - holds the program's commands.

![](/assets/assembly-1.png)

