# 👻 Indicators of Compromise (IOCs) – Ghost RAT 🌏

---

## 🔍 Overview

This document outlines behavior-based **Indicators of Compromise (IOCs)** extracted from Ghost RAT during dynamic analysis with **Vortex (powered by Cyberstanc)**.  
These artifacts expose the malware’s internal functionality — including **execution flow**, **persistence mechanisms**, **anti-analysis behavior**, and **system-level manipulation**.

---

## 📌 Core IOC Categories

| **IOC**                         | **Namespace**                                      | **Functionality / Behavior**                  |
|----------------------------------|----------------------------------------------------|-----------------------------------------------|
| `copy file`                      | host-interaction/file-system/copy                  | Copies payload or artifacts to hidden paths   |
| `move file`                      | host-interaction/file-system/move                  | File relocation to evade detection            |
| `inject dll / inject thread`    | host-interaction/process/inject                    | Memory injection into target processes        |
| `create mutex`                  | host-interaction/mutex                             | Prevents redundant execution; stealth tactic  |
| `create service / start service`| host-interaction/service/create, /start            | Persistence through system services           |
| `modify service`                | host-interaction/service/modify                    | Hijacks or updates existing services          |
| `create process (suspended)`    | host-interaction/process/create                    | Creates suspended processes for stealth       |
| `acquire debug privileges`      | host-interaction/process/modify                    | Enables advanced access for tampering         |
| `terminate process`             | host-interaction/process/terminate                 | Disables security or unwanted processes       |
| `check OS version`              | host-interaction/os/version                        | Determines host system to tailor behavior     |
| `accept command line arguments` | host-interaction/cli                               | Supports dynamic runtime instructions         |
| `reference Base64 string`       | data-manipulation/encoding/base64                  | Used for obfuscating strings/data             |
| `reference anti-VM strings`     | anti-analysis/anti-vm/vm-detection                 | Detects VMs, sandboxes, or forensic tools     |
| `GetTickCount` / delay check    | anti-analysis/anti-debugging/debugger-detection    | Timing-based anti-debugging defense           |
| `kernel32 resource unpacking`   | executable/resource                                | Extracts payload dynamically at runtime       |
| `embedded PE in .rsrc`          | executable/subfile/pe / pe/section/rsrc            | Hidden executables inside resource section    |
| `query/modify registry`         | host-interaction/registry                          | Alters startup config and gains persistence   |
| `create directory`              | host-interaction/file-system/create                | Prepares folders for dropped artifacts        |
| `delete file`                   | host-interaction/file-system/delete                | Cleans up dropped files or traces             |

---

## 🧠 Observational Highlights

- 🎯 Emphasizes stealth through **mutex creation**, **service hijacking**, and **runtime unpacking**
- 🛡️ Evades detection with **environment checks** and **anti-debug delay loops**
- 🧬 Maintains control using **thread injection**, **command-line argument parsing**, and **registry edits**

---

## 🎯 Threat Analyst Notes

These IOCs are highly valuable for **endpoint detection**, **SOC alert correlation**, and **YARA rule tuning**.  
When observed together, they strongly signal the presence of **Ghost RAT or APT17-linked malware strains**.

---

**Stay curious. Stay safe. Stay ahead.**

