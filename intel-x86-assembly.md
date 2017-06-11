# Intel x86 Assembly

 Assembly Basics

	• Two main forms of assembly syntax: AT&T and Intel

	• AT&T syntax is used by the GNU Assembler, contained in the gcc compiler, often used by Linux devs

	• Intel syntax assemblers, Netwide Assembler \(NASM\) is most common.

		○ Used by many windows assemblers and debuggers.

	• Styles of format:

		•  The source and destination operands are reversed, and different symbols are used to mark the beginning of a comment:

		•  NASM format CMD &lt;dest&gt;, &lt;source&gt; &lt;; comment&gt;

		•  AT&T format CMD &lt;source&gt;, &lt;dest&gt; &lt;\# comment&gt;

		•  AT&T format uses a % before registers; NASM does not.

		•  AT&T format uses a $ before literal values; NASM does not.

•  AT&T handles memory references differently than NASM.

## Commands

| NASM Syntax | NASM Example | AT&T Example |
| :--- | :--- | :--- |
| mov &lt;dest&gt;, &lt;source&gt; | mov eax, 51h ;comment | movl $51h, %eax \#comment |



