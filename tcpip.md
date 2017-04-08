# TCP/IP

Layer 4 technology

#### Transmission Control Block \(TCB\)

TCP requires that each session is unique and handled independently. 

Transmission Control Block \(TCB\) is a data structure that stores information about each session and its state.

TCB holds the following information:

1. Two socket numbers \(sender TCP socket, receiver TCP socket\)
2. Pointers to buffers incoming and outgoing data is stored
3. number of bytes received and acknowledged 
4. number of bytes received and not acknowledged
5. Current window size

Each device \(sender, receiver\) maintains its own TCB



