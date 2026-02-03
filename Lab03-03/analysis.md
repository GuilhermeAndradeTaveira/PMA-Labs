# Lab 03-03 Basic Static Analysis
## Sample Information
**Files:**

- lab03-03.exe
  - MD5: e2bf42217a67e46433da8b6f4507219e
### 1. What do you notice when monitoring this malware with Process Explorer?

**Initially, the malware initiates as Lab03-03.exe and then changes to svchost.exe (PID 1812)**

### 2. Can you identify any live memory modifications?

**The disk image shows that the process is not the same as its disk image.**

### 3. What are the malware’s host-based indicators?

**The malware creates the file praticalmalwareanalysis.log**

### 4. What is the purpose of this program

**This malware is a keylogger, if you open the log it created, you can see it detects which keys you pressed and writes it into the log file.**

## IOCs

- Creates log file
  - praticalmalwareanalysis.log - (cant put the hash since its a keyloggers log file.)

- Disguises itself as and svchost.exe, initially starts up as Lab03-03.exe creates the svchost.exe as its thread then load its information in it.
