# 🚨 Indicators of Compromise (IOCs) - Ghost RAT

---

## 🧠 Overview

This document outlines behavior-based Indicators of Compromise (IOCs) extracted during the analysis of Ghost RAT using **Vortex (powered by Cyberstanc)**.  
These IOCs highlight the malware’s core capabilities: persistence, injection, evasion, and system manipulation.

---

## 🧾 Key IOCs Identified

| **IOC**                         | **Namespace**                                      | **Description**                               |
|----------------------------------|----------------------------------------------------|-----------------------------------------------|
| copy file                        | host-interaction/file-system/copy                  | Copies payload or additional components       |
| move file                        | host-interaction/file-system/move                  | Moves executable to stealth locations         |
| inject dll / inject thread      | host-interaction/process/inject                    | Code injection into other processes           |
| create mutex                    | host-interaction/mutex                             | Used to prevent duplicate execution           |
| create service / start service | host-interaction/service/create, /start            | Establishes persistence on startup            |
| modify service                  | host-interaction/service/modify                    | Alters existing services for stealth          |
| create process (suspended)      | host-interaction/process/create                    | Spawns new process in suspended state         |
| acquire debug privileges        | host-interaction/process/modify                    | Used for evasion or advanced control          |
| terminate process               | host-interaction/process/terminate                 | Kills unwanted or security processes          |
| check OS version                | host-interaction/os/version                        | Determines host environment type              |
| accept command line arguments   | host-interaction/cli                               | Enables runtime control via arguments         |
| reference Base64 string         | data-manipulation/encoding/base64                  | Signs of obfuscated or encoded data           |
| reference anti-VM strings       | anti-analysis/anti-vm/vm-detection                 | Detects virtualized analysis environments     |
| check for delay via GetTickCount| anti-analysis/anti-debugging/debugger-detection    | Timing-based anti-debugging                   |
| extract resource via kernel32   | executable/resource                                | Payload unpacking during execution            |
| contain embedded PE / .rsrc     | executable/subfile/pe / pe/section/rsrc            | Drops or unpacks hidden PE files              |
| query registry / modify registry| host-interaction/registry                          | Reads or alters registry keys                 |
| create directory                | host-interaction/file-system/create                | Creates folders for dropped components        |
| delete file                     | host-interaction/file-system/delete                | Removes evidence or logs                      |

---

## 🧠 Summary

These IOCs reflect Ghost RAT’s operational goals: stealthy installation, persistence, host control, and sandbox evasion.  
They are critical for detection and threat hunting across endpoints and networks.

**Stay curious. Stay safe. Stay ahead.**
