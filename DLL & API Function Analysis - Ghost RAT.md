#  DLL & API Function Analysis – Ghost RAT 👻

---

## 🔍 Overview

This section highlights the **Windows DLLs and API functions** imported and executed by Ghost RAT.  
These interactions are critical for enabling **process control**, **persistence**, **stealth**, and **execution flow manipulation** — hallmarks of advanced remote access tools used in cyber-espionage.

---

## 🧠 Key DLLs & Their Role

| **DLL**        | **Functions (Examples)**                                               | **Behavioral Role**                                                          |
|----------------|------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| `ole32.dll`    | `CoCreateGuid`, `CoInitialize`, `CoUninitialize`                      | COM object handling and unique identifier creation                           |
| `MSVCRT.dll`   | `strcpy`, `malloc`, `free`, `fopen`, `fwrite`, `rand`, `sprintf`      | Core memory allocation, file I/O, and runtime logic                         |
| `USER32.dll`   | `CreateWindowExA`, `MessageBoxW`, `GetMessageA`                       | GUI creation — often used as distraction or decoy                           |
| `SHELL32.dll`  | `ShellExecuteA`                                                       | Executes files or scripts using Windows Shell                               |
| `ADVAPI32.dll` | `RegOpenKeyExA`, `RegSetValueExA`, `OpenProcessToken`, `AdjustTokenPrivileges` | Grants privilege escalation, alters startup behavior                       |
| `KERNEL32.dll` | `CreateProcessA`, `OpenProcess`, `CreateRemoteThread`, `GetTickCount`, `Sleep`, `ReadFile`, `WriteFile` | Enables process injection, anti-debugging, timing control, and system interaction |

---

## 🧪 Notable Behavioral Insights

- **🧬 Injection & Remote Thread Execution**  
  `CreateRemoteThread` + `VirtualAllocEx` + `WriteProcessMemory` confirm **memory-based code injection**.

- **🧷 Persistence Techniques**  
  Use of `RegSetValueExA` + `ShellExecuteA` implies **autorun key planting** or **shell-based loader initiation**.

- **🛡️ Anti-Debugging & Sandbox Evasion**  
  `GetTickCount`, `Sleep`, and `OutputDebugStringA` introduce **timing checks** and **conditional exits** if analysis tools are detected.

- **🗃️ File and Log Manipulation**  
  `CreateFileA`, `ReadFile`, `WriteFile`, and `DeleteFileA` indicate potential **log access, tampering, or payload staging**.

---

## 🧠 Final Assessment

Ghost RAT leverages a sophisticated blend of Windows API calls to maintain control over the infected system.  
Its modular use of `KERNEL32.dll`, `ADVAPI32.dll`, and `USER32.dll` APIs shows classic behavior tied to **targeted nation-state implants**.

These API calls enable Ghost RAT to:
- ✴ Maintain **long-term stealth**  
- ✴ Perform **low-level execution control**  
- ✴ Evade analysis platforms  
- ✴ Escalate privileges for persistence and data access

---

**Stay curious. Stay safe. Stay ahead.**

