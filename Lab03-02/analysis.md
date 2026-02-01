# Lab Lab03-02: Basic Dynamic Analysis
## Sample Information
**Files:**

- lab03-02.dll
  - MD5: 84882c9d43e23d63b82004fae74ebb61
###  1. How can you get this malware to install itself?

**This malware has some exports that indicate that it can install itself (Install,InstallA) using the rundll32.exe with rundll32.exe Lab03-02.dll, installA**

### 2. How would you get this malware to run after installation?

**To run the malware, you need to start the service it created using. The name of the service is IPRIP**

### 3. How can you find the process under which this malware is running?

**To find the process, you have to use process explorer and filter by the dll name to find the correct process (in this case a svchost.exe pid 1332)**

### 4. Which filters could you set in order to use procmon to glean information?

**You can filter by PID found in the process explorer.**

### 5. What are the malware’s host-based indicators?

**The malware creates a file called "wbemcore.log" (absolute path:C:\WINDOWS\system32\wbem\Logs\wbemcore.log), reads files (INDEX.BTR, OBJECTS.DATA), creates a thread (TID: 2960), alter and create registries and install itself in the registry HKLM\SYSTEM\CurrentControlSet\Services\IPRIP\Parameters\ServiceDll**

### 6. Are there any useful network-based signatures for this malware?

**In wireshark, by filtering the packets with tcp.port == 80, we can see it does an GET for the domain praticalmalwareanalysis.com to get the file serve.htmll**


