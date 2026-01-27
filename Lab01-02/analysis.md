# Lab 01-01: Basic Static Analysis
## Sample Information
**Files:**
- lab01-02.exe
  - MD5: 8363436878404da0ae3e46991e355b83


### 1. Upload the Lab01-02.exe file to http://www.VirusTotal.com/. Does it match any existing antivirus definitions?

**Yes, many security vendors classify it as a trojan.**

### 2. Are there any indications that this file is packed or obfuscated? If so, what are these indicators? If the file is packed, unpack it if possible

**Yes, this file is packed. When we open it with Detect it Easy we can see that he was packed using UPX, a open-source packer, in various sections. Also, when we try to analyze the imports using PEStudio there is almost nothing there, indicating that the file is packed.**

### 3. Do any imports hint at this program’s functionality? If so, which imports are they and what do they tell you?

**Imports:yGetModuleFileNameA,CreateWaitableTimerA,SystemTimeToFileTime,OpenMutexA,SetWaitableTimer,WaitForSingleObject, CreateMutexA,CreateThread,CreateServiceA,StartServiceCtrlDispatcherA,OpenSCManagerA,InternetOpenURLA,InternetOpenA. These imports show that this malware can install itself persistently via services and initiate on login, wait for some Object to release the lock, run other routines, schedule its own execution and access the internet to download or upload something. So, this malware appears to be a trojan/backdoor that can installar itself as a windows service**

### 4. What host- or network-based indicators could be used to identify this malware on infected machines?

**Looking into the hardcoded strings, we can see an URL (http://www.malwareanalysisbook.com) and internet explorer 8.0, meaning it could possibly access sites via that browser**

