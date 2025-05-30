# 🧬 DLL & API Function Analysis - Ghost RAT

---

## 🔍 Overview

This section highlights the **Windows DLLs and API functions** imported by the Ghost RAT sample.  
These functions reveal how the malware interacts with the operating system, processes, memory, and registry.

---

## 🗂️ Key DLLs Observed

- **ole32.dll**  
  `CoCreateGuid`, `CoInitialize`, `CoUninitialize`

- **MSVCRT.dll**  
  `strcpy`, `malloc`, `free`, `fopen`, `fwrite`, `sprintf`, `rand`, etc.

- **USER32.dll**  
  `CreateWindowExA`, `MessageBoxW`, `GetMessageA`, etc.

- **SHELL32.dll**  
  `ShellExecuteA`

- **ADVAPI32.dll**  
  `RegOpenKeyExA`, `RegSetValueExA`, `OpenProcessToken`, `AdjustTokenPrivileges`

- **KERNEL32.dll**  
  `CreateProcessA`, `OpenProcess`, `CreateRemoteThread`, `GetTickCount`, `Sleep`, `ReadFile`, `WriteFile`

---

## 📌 Notable Behavior Inferred

- **Injection & Execution**  
  `CreateRemoteThread`, `VirtualAllocEx`, and `WriteProcessMemory` suggest memory injection.

- **Persistence**  
  Functions like `RegCreateKeyExA` and `ShellExecuteA` indicate registry and shell-based persistence.

- **Evasion**  
  `GetTickCount`, `OutputDebugStringA`, and `IsDebuggerPresent` show anti-analysis/sandbox evasion.

- **File and Process Manipulation**  
  Calls to `CreateFileA`, `DeleteFileA`, `ReadFile`, and `WriteFile` show interaction with local resources.

---

Ghost RAT leverages these APIs across multiple DLLs to maintain stealth, gain persistence, and control the infected system — behavior consistent with advanced, targeted malware.
