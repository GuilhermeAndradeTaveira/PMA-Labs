# Lab 01-01: Basic Static Analysis
## Sample Information
**Files:**
- lab01-01.exe
  - MD5: bb7425b82141a1c0f7d60e5106676bb1
- lab01-01.dll
  - MD5: 290934c61de9176ad682ffdd65f0a669

### 1. Upload the files to http://www.VirusTotal.com/ and view the reports. Does either file match any existing antivirus signatures?

**Yes, both lab01-01.exe and lab01-01.dll match malicious signatures detected by many antivirus vendors.**

### 2. When were these files compiled?

**These files were compiled on 12/19/2010, one minute apart from each other.**

### 3. Are there any indications that either of these files is packed or obfuscated? If so, what are these indicators?

**There are no indications that these files are packed or obfuscated. When loading the files into Detect It Easy (DIE), no packer is detected. Additionally, using Dependency Walker, it is possible to observe many imported functions, which suggests that the files are not packed. To further confirm this, an analysis with PEStudio shows low entropy values and a large number of imports, reinforcing the conclusion that the files are not packed.**

### 4.Do any imports hint at what this malware does? If so, which imports are they

**The file lab01-01.exe imports functions related to file manipulation (create, open, find, and copy). The lab01-01.dll imports functions that indicate the ability to create processes, acquire mutex locks, and remain idle for periods of time.
Relevant imports include: Sleep, CreateMutexA, CreateProcessA, OpenMutexA, CreateFileA, FindNextFileA, FindFirstFileA, CopyFileA**

### 5.Are there any other files or host-based indicators that you could look for on infected systems?

**Yes. Based on the analysis performed, this malware is capable of creating processes and creating or modifying files. These actions could serve as host-based indicators if they were monitored by an analyst.**

### 6. What network-based indicators could be used to find this malware on infected machines?

**The DLL imports the connect and socket functions, indicating that it may communicate with a command-and-control server. Also, the DLL contains a IP address (127.26.152.13).**

### 7. What would you guess is the purpose of these files?

**Based off the IP Address we found and the socket and connection imports, these files are probably a backdoor**
