# Dynamic Analysis

## Sandboxing

* Malware sandboxes
* * Norman SandBox
  * GFI SandBox
  * Anubis
  * Joe Sandbox
  * ThreatExpert
  * BitBlaze
  * Comodo Instant Malware Analysis

## Running Malware

* Launching DLLs successfully using rundll32.exe

`C:\> rundll32.exe DLLname, Export arguments`

* Export value must be a function name/ordinal selected from exported function table in the DLL.
* **Process Monitor **for Windows can be a useful tool to analyze system calls that are made by a running process.
* * Filtering captured events:
  * * Process Name
    * Operation
    * Detail
* **ProcMon** provides important info:
* * Registry - by examining registry operations, you can tell how malware installs itself
  * FS - file system interaction shows all files that the malware creates or config files it uses
  * Process Activity - can tell if malware spawns additional processes
  * Network - identifying network connections show you any port malware is listening on.
* **Process Explorer**
* * Services = pink
  * Processes = blue
  * New Processes = green
  * Terminated processes = red
  * Can run a verify command that can verify the image on disk that is signed binary.
  * * Can be thwarted with Process Replacement - involves running a process on system and overwriting its memory space with a malicious exec.
    * Offers malware the same privileges as process it is replacing
    * The image in memory differs from image on disk
* **RegShot**
* * Open source registry comparison tool: compare two registry snapshots



