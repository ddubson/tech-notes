# Addressing & Byte Ordering

Conventions of object addressing

* For multi-byte objects \(i.e. int\), two things have to be established:
  The address, Order of bytes in memory

## Addressing

Example: for int variable x with the value of &x as 0x100, its contiguous memory locations would be:

```
0x100, 0x101, 0x102, 0x103
```

\(int is a 32-bit type, each memory location holds a byte, 4 bytes in 32 bits, 4 memory locations to represent one integer\)

### Ordering of bytes in memory

![](/assets/byte-order-1.png)

When byte order matters:

* * When binary data is transmitted over a network between different machines.
  * Looking at byte sequences representing integer data



