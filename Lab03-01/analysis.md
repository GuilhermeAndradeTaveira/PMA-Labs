# Lab 01-01: Basic Static Analysis
## Sample Information
**Files:**
- lab03-01.exe
  - MD5: d537acb8f56a1ce206bc35cf8ff959c0


### 1. What are this malware’s imports and strings?

**The malware appears to be packed. The only import is ExitProcess, the strings do not seem obfuscated tho**

### 2. What are the malware’s host-based indicators?

**This malware creates registries and puts itself in system32 as vmx32to64.exe**

### 3. Are there any useful network-based signatures for this malware? If so, what are they?\

**The malware resolves www.praticalmalwareanalysis.com**


## Disclaimer

**I've had some problems trying to run this sample, the werFault.exe always appeared and I was unable to disable it, making the analysis very hard. If you had the same problem, try to run it on a windows XP vm, this book is quite old so a lot of the samples here were designed for older versions of windows.**
