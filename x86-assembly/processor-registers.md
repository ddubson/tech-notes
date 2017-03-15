# Intel x86 Registers

| Register Category | Register Name | Purpose | Reg Size \(Bits\) |
| :--- | :--- | :--- | :--- |
| General Registers | EAX, EBX, ECX, EDX | Used to manipulate data \(Extended\) | 32 |
|  | AX, BX, CX, DX | 16-bit version of extended registers | 16 |
|  | AH, BH, CH, DH, AL, BL, CL, DL | 8-bit high and low-order bytes of above | 8 |
| Segment Registers | CS, SS, DS, ES, FS, GS | Holds the first part of a memory address; holds pointers to code, stack, and extra data segments | 16 |
| Offset Registers |  | Indicates an offset related to segment registers |  |
|  | EBP \(Ext. Base Pointer\) | Points to beginning of local block for a function | 32 |
|  | ESI \(Ext. Source Index | Holds the data source offset in an operation using a mem. block | 32 |
|  | EDI \(Ext. Destination Index\) | Holds the destination data offset in an operation using a memory block | 32 |
|  | ESP \(Ext. Stack Pointer | Points to top of stack | 32 |
| Special Registers |  | Only used by CPU |  |
|  | EFLAGS Register: ZF=Zero Flag; IF=Interrupt enable flag; SF = Sign flag | Used by CPU to track state |  |
|  | EIP \(Ext. Instruction Ptr\) | Points to the address of the next instruction. | 32 |



# 



