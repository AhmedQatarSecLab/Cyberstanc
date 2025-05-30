# Ghost RAT Malware Analysis Report

**Analyst**: Ahmed Qatar  
**Tool Used**: Vortex (Powered by Cyberstanc)  
**Environment**: VMware + Wireshark  
**Date**: [25May 2025]

---

## 🧠 Overview

Ghost RAT is a Remote Access Trojan (RAT) attributed to **APT17**, a Chinese nation-state threat group.  
It is used in **state-sponsored cyber-espionage campaigns** targeting:

- 🏛️ Government agencies  
- 🛡️ Military systems  
- ⚡ Critical infrastructure  
- 🧠 Political and strategic entities  

---

## 🔬 Lab Summary

- Malware sample sourced from: **MalwareBazaar**  
- Environment: **Isolated VMware VM**  
- Network capture: **Wireshark**  
- Behavioral analysis: **Vortex (Cyberstanc)**

---

## 🎥 Lab Execution Video

Watch the full Ghost RAT lab execution here:  
👉 Watch the full [Ghost RAT Lab](https://drive.google.com/file/d/1w2KuczLkKZIVF_t1WKmg0caVo24IfAeN/view?usp=drive_link) execution video.



---

## 🚨 Key Indicators of Compromise (IOCs)

- **DLL and thread injection**  
- **Process creation & manipulation (suspended, modified I/O)**  
- **Persistence via Windows services**  
- **Mutex creation & anti-VM detection**  
- **Encoded payloads (Base64 & XOR)**  
- **Registry key access and modification**  
- **File system changes (move, delete, copy)**

---

## 🛠️ Tools Used

- **Vortex** – for malware behavior analysis  
- **Wireshark** – to capture and monitor network activity  
- **VMware** – to safely execute malware in a sandboxed environment

---

## 🎯 Conclusion

Ghost RAT’s behavioral profile reveals its use in **targeted cyber operations**.  
Vortex’s detailed reporting enabled rapid identification of the threat’s core capabilities, confirming its classification as a **persistent, state-sponsored espionage tool**.

---

## 🙏 Credits

Special thanks to **Cyberstanc** for developing Vortex, and to **Rohit Bankoti** for the opportunity to explore this tool hands-on.

**Stay curious. Stay safe. Stay ahead.**


