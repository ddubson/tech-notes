# Addressing Modes

There are many ways to indicate the effective address to manipulate memory, called addressing modes:

| Addressing Mode | Description | NASM Examples |
| :--- | :--- | :--- |
| Register | Register holds the data to be manipulated. No memory interaction. Registers must be same size. | mov ebx, edx \|\| add al, ch |
| Immediate | The source operand is a numerical value. Decimal is assumed, use 'h' for Hex | mox eax, 1234h \|\| mov dx, 301 |
| Direct | The first operand is the address of the memory to manipulate. Marked with brackets. | mov bh, 100 && mov\[4321\], bh |
| Register indirect | The first operand is a register in brackets that holds the address to be manipulated | mov \[di\], ecx |
| Based relative | The effective addr. to be manipulated is calculated by using ebx or ebp plus an offset value. | mov edx, 20\[ebx\] |
| Indexed relative | Same as based relative, but edi and esi are used to hold the offset | mov ecx, 20\[esi\] |
| Based Indexed-relative | The effective address is found by combining Based and Indexed Relative modes. | mov ax, \[bx\]\[si\]+1 |



