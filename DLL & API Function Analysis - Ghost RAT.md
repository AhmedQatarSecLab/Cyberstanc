# 🧬 DLL & API Function Analysis - Ghost RAT

---

## 🔍 Overview

This section highlights the **Windows DLLs and API functions** imported by the Ghost RAT sample.  
These libraries enable the malware to interact with the operating system for execution, evasion, persistence, and resource manipulation.

---

## 🗂️ Key DLLs Observed

| **DLL**        | **Functions (Examples)**                                               | **Purpose**                                                                 |
|----------------|------------------------------------------------------------------------|------------------------------------------------------------------------------|
| `ole32.dll`    | `CoCreateGuid`, `CoInitialize`, `CoUninitialize`                      | Initializes COM objects and services, used for GUID creation                |
| `MSVCRT.dll`   | `strcpy`, `malloc`, `free`, `fopen`, `fwrite`, `rand`, `sprintf`      | C runtime functions for memory, file handling, and string operations       |
| `USER32.dll`   | `CreateWindowExA`, `MessageBoxW`, `GetMessageA`                       | GUI manipulation and message handling (can be used as a decoy)             |
| `SHELL32.dll`  | `ShellExecuteA`                                                       | Executes programs or files through the Windows Shell                       |
| `ADVAPI32.dll` | `RegOpenKeyExA`, `RegSetValueExA`, `OpenProcessToken`, `AdjustTokenPrivileges` | Registry manipulation and privilege escalation                            |
| `KERNEL32.dll` | `CreateProcessA`, `OpenProcess`, `CreateRemoteThread`, `GetTickCount`, `Sleep`, `ReadFile`, `WriteFile` | Core system interaction: process/thread control, anti-debugging, file I/O  |

---

## 📌 Notable Behavior Inferred

- **Injection & Execution**  
  Use of `CreateRemoteThread`, `VirtualAllocEx`, and `WriteProcessMemory` indicates classic memory injection techniques.

- **Persistence**  
  Calls to `RegCreateKeyExA` and `ShellExecuteA` suggest the malware creates autorun keys and triggers execution via shell integration.

- **Evasion**  
  `GetTickCount`, `OutputDebugStringA`, and `IsDebuggerPresent` are used to detect sandboxed or debugged environments.

- **File and Process Interaction**  
  API calls like `CreateFileA`, `DeleteFileA`, `ReadFile`, and `WriteFile` show manipulation of system resources and potential log tampering.

---

## 🧠 Summary

Ghost RAT imports a wide array of Windows APIs across multiple DLLs to perform system-level operations.  
These interactions enable it to **inject code**, **escalate privileges**, **evade detection**, and **persist** across reboots — all traits commonly seen in **advanced, state-sponsored threats**.

**Stay curious. Stay safe. Stay ahead.**
