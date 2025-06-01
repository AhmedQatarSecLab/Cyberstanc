# 👻 Ghost RAT Malware Analysis Report 🌏

**Tool Used**: Vortex (Powered by Cyberstanc)  
**Environment**: VMware + Wireshark  
**Sample Source**: MalwareBazaar  
**Date**: 25 May 2025

---

## 1. Overview

Ghost RAT is a Remote Access Trojan attributed to **APT17**, a Chinese nation-state threat actor.  
It has been used in multiple **cyber-espionage campaigns** targeting:

- 🏛️ Government agencies  
- 🛡️ Military infrastructure  
- ⚙️ Critical systems  
- 🏳️ Political & strategic entities

---

## 2. Execution Environment

- 🔬 **Lab Setup**: Isolated VMware machine 🖥️
- 📡 **Network Monitor**: Wireshark 🦈
- 🧪 **Behavioral Analysis**: Vortex 🦚 (powered by Cyberstanc)

---

## 3. Malicious Function Analysis

### 3.1 Anti-Analysis Mechanisms

- 🔍 Checks for environment variables (`getenv`)  
- 🛡️ Uses `CreateToolhelp32Snapshot()` to enumerate processes  
- 🧩 Designed to avoid sandbox/debuggers (`GetTickCount`, mutex checks)



### 3.2 Resource Loading & Decryption

- 🔐 Allocates memory for encrypted payload  
- 🧩 Custom decryption in 1024-byte blocks  
- 📦 Resources decrypted in stages to bypass static detection

---

### 3.3 Dynamic Execution

- 📥 Uses `LoadLibrary()` and `GetProcAddress()`  
- 🎯 Executes via function pointers  
- 🔄 Dynamically resolves API calls for obfuscation

---

### 3.4 Obfuscation Techniques

| Technique                 | Description                                             |
|--------------------------|---------------------------------------------------------|
| String Obfuscation       | Encrypted strings decoded at runtime                    |
| Control Flow Obfuscation | Complex logic and redirection to delay analysis         |
| Resource Packing          | Payload hidden in encrypted binary sections            |
| Anti-Debug Checks         | Uses time-based checks & process comparisons           |

---

## 4. Threat Capabilities

| Capability           | Level   | Evidence                                      | Risk |
|----------------------|---------|-----------------------------------------------|------|
| 🕵️ Stealth          | High    | Anti-VM, obfuscation, mutex, debugger evasion | 🔴   |
| ♻️ Persistence       | Medium  | Service creation and registry access          | 🟠   |
| 📤 Data Exfiltration | High    | C2-style behavior and credential targeting    | 🔴   |
| 🔧 System Mod        | Likely  | Process/thread injection & service tampering  | 🟠   |

---

## 5. Indicators of Compromise (IOCs)

- `CreateRemoteThread`, `WriteProcessMemory`  
- `RegCreateKeyExA`, `ShellExecuteA`  
- `LoadLibrary`, `CreateService`, `GetTickCount`  
- `.rsrc section`, Base64/XOR encoded strings  
- Mutex strings and anti-debug logic

---

## 6. DLL & API Behavior Summary

| **DLL**        | **Functions (Examples)**                                               | **Purpose**                                                                 |
|----------------|------------------------------------------------------------------------|------------------------------------------------------------------------------|
| `ole32.dll`    | `CoCreateGuid`, `CoInitialize`                                         | COM object interaction and GUID generation                                 |
| `MSVCRT.dll`   | `malloc`, `fopen`, `fwrite`, `sprintf`                                 | Memory allocation, file handling, and string operations                    |
| `USER32.dll`   | `CreateWindowExA`, `MessageBoxW`                                       | User interface handling (sometimes as decoy)                               |
| `SHELL32.dll`  | `ShellExecuteA`                                                        | Execute files/programs via Windows shell                                   |
| `ADVAPI32.dll` | `RegOpenKeyExA`, `AdjustTokenPrivileges`                               | Registry interaction and privilege elevation                               |
| `KERNEL32.dll` | `CreateProcessA`, `OpenProcess`, `WriteFile`, `Sleep`, `GetTickCount`  | Process/thread management, file I/O, anti-analysis                         |

---

## 🎥 7. Lab Execution Video

📺 👉 [Watch Ghost RAT Lab Execution](https://drive.google.com/file/d/1w2KuczLkKZIVF_t1WKmg0caVo24IfAeN/view?usp=drive_link)

---

## 🎯 8. Conclusion

Ghost RAT is a highly persistent, evasive, and stealthy threat used in **state-sponsored cyber operations**.  
Through **Vortex’s automated analysis**, all behavioral patterns — including DLL injection, anti-debugging, and file system manipulation — were clearly observed and documented.

The threat demonstrates characteristics consistent with APT17 campaigns, particularly in espionage-related attacks.

---

## 🙏 9. Credits

Thanks to **Cyberstanc** for providing access to Vortex, and to **Rohit Bankoti** for the opportunity to explore real-world threat scenarios during the internship.

**Stay curious. Stay safe. Stay ahead.**



