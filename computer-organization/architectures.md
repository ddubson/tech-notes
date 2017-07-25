# Computer Architectures

## Von Neumann Architecture \(Princeton Architecture\)

Design architecture for a system that has:

* processing unit containing:
  * ALU \(Arithmetic Logic Unit\)
  * Processor Registers
* Control unit
  * Instruction register
  * Program Counter
* Memory \(both data and instructions\)
* External mass storage
* I/O devices

**Von Neumann Bottleneck **- an instruction fetch and a data processing instructions cannot be simultaneously executed since memory is both for instructions and data.

## Harvard Architecture

Computer architecture that is based on separate storage and signal pathways for instructions and data.

* Instruction memory and Data memory can be of differing word width, implementation, etc. so no need to share characteristics
* Instruction memory can be purely read-only vs data memory which can be read-write capable.

## Modified Harvard Architecture

Modified subset of Harvard Architecture with the distinction that instruction memory can be accessed as if it were data.

Most modern CPUs are built in a Modified Harvard Architecture design.

