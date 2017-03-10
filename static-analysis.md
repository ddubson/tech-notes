# Static Analysis

## Pack and Obfuscation

Use program PEiD

* Portable Executable \(PE\) file format is used by Win executables, object code, and DLLs.
* PE files begin with a header that includes information about the code, the type of app, required lib functions, and space requirements.

---

## Linked Libraries / Functions

* Imports to an executable is extremely valuable
* * Code libraries can be connected to executable by
    linking
* Knowing how library code is linked is critical to understanding malware.

### Static, Runtime, and Dynamic Linking

* Static Linking - least commonly used, common in UNIX and Linux programs.
* * When a library is statically linked, all code from the library is copied into executable, which makes exec grow in size.
* Runtime Linking - commonly used in malware, especially when packed and obfuscated.
* * Executables connect to libraries only when that function is needed, not at program start, as with dynamically linked programs.
  * Several of MS-Win functions allow to import linked functions not listed in program's header.
  * * LoadLibrary - allow a program to access any function in any library on the sys.
    * GetProcAddress - similar to LoadLibrary
    * LdrGetProcAddress
    * LdrLoadDll
  * Most common and most interesting for malware analysts
  * When libraries are linked, the host OS searches for the necessary libraries when the program is loaded.
* PE file header stores all information about every library that will be loaded and every functions that will be used.
* This gives analysts clues as to the function of the malware itself.

### Exploring Dynamically Linked Functions

* **Dependence Walker **- application for Windows that peruses through PE header - lists only dynamically linked libraries.
* A program's DLL can tell you a lot about its function
* Common DLLs to look at

Common DLLs

| DLL | Description |
| :--- | :--- |
| Kernel32.dll | This is a very common DLL that contains core functionality, such as access and manipulation of memory, files, and hardware. |
| Advapi32.dll | This DLL provides access to advanced core Windows components such as the Service Manager and Registry. |
| User32.dll | This DLL contains all the user-interface components, such as buttons, scroll bars, and components for controlling and responding to user actions. |
| Gdi32.dll | This DLL contains functions for displaying and manipulating graphics. |
| Ntdll.dll | This DLL is the interface to the Windows kernel. Executables generally do not import this file directly, although it is always imported indirectly byKernel32.dll. If an executable imports this file, it means that the author intended to use functionality not normally available to Windows programs. Some tasks, such as hiding functionality or manipulating processes, will use this interface. |
| WSock32.dllandWs2\_32.dll | These are networking DLLs. A program that accesses either of these most likely connects to a network or performs network-related tasks. |
| Wininet.dll | This DLL contains higher-level networking functions that implement protocols such as FTP, HTTP, and NTP. |



* Function names ending with Ex -&gt;backwards compatible suffix created by MS for old functions
* Function params that take A or W at end of names -&gt;one for ASCII strings and one for Wide Char \(Unicode\)

## Imported Functions

* The names of the imported functions can give you a good idea about what the exec does.

## Exported Functions

* DLLs and EXEs export functions to interact with other programs and code.
* Typically, a DLL implements one or more functions and exports them for use by an executable that can then import and use them.
* DLLs are specifically implemented to provide functionality used by EXEs.
* EXEs are not designed to provide functionality for other EXEs, so exported functions are rare.
* Discovering exports in an EXE will often provide useful information

# PE File Headers and Sections

* PE file format contains a header followed by a series of sections
* Most common sections of a PE:
* * **.text **- contains CPU instr.; only section that can execute.
  * **.rdata** - typically contains import/export info;
  * * Can store other read-only data.
    * Sometimes .idata and .edata section -&gt; import/export info
  * **.data** - contains program's global data, accessible from anywhere. Local data is not stored, or anywhere else in the PE.
  * **.rsrc** - includes the resources used by the exec that are not considered part of the exec, such as icons, images, menus, and strings.
* Section names are often consistent across a compiler, but can vary across different compilers.
* * VS uses .text, but Borland Delphi uses CO

Sections of a PE File for a Windows Executable

| Executable | Description |
| :--- | :--- |
| .text | Contains the executable code |
| .rdata | Holds read-only data that is globally accessible within the program |
| .data | Stores global data accessed throughout the program |
| .idata | Sometimes present and stores the import function information; if this section is not present, the import function information is stored in the.rdatasection |
| .edata | Sometimes present and stores the export function information; if this section is not present, the export function information is stored in the.rdatasection |
| .pdata | Present only in 64-bit executables and stores exception-handling information |
| .rsrc | Stores resources needed by the executable |
| .reloc | Contains information for relocation of library files |

## Examining with PEview

* PEview tool can browse through the information in a binary header.
* E.g. analysis of a IMAGE\_NT\_HEADERS/IMAGE\_FILE\_HEADER header can yield the compilation date time, can give clue of when the program was introduced.
* * Delphi programs embed a compile time of June 19th, 1992 -&gt; indication that the exec is a Delphi program
  * Malware authors can easily fake compile time info
* IMAGE\_OPTIONAL\_HEADER includes the Subsystem description -&gt; Console or GUI application.
* IMAGE\_SECTION\_HEADER,
* * Virtual Size: how much space is allocated for a section during loading.
  * Size of Raw Data: shows how big the section is on disk
  * The two values above should be about equal
* Section sizes can be useful in detecting packed executables.
* * If virtual size is much larger than Size of Raw Data: often indicative of packed code

## Viewing the Resource Section with Resource Hacker

* View the .rsrc section for additional details on binary



