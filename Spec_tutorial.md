# How to Recreate a Full System Diagnostic File (Unified All‑in‑One Version)

## PART A — WHAT YOU ARE RECREATING

You are rebuilding a **consolidated system diagnostic report** composed of:

• Windows system commands
• Built‑in diagnostic tools
• Third‑party hardware health tools
• Manual observations

All inputs are **normalized into one structured master text file** with:

• Fixed section order
• One section per command or capture
• Consistent labels
• Human‑readable explanations

---

## PART B — FILE SETUP (DO THIS FIRST)

Create a folder on the target PC named:

```
PC_DIAGNOSTICS_RAW
```

Inside this folder, create **ONE file only**:

```
FULL_SYSTEM_DIAGNOSTIC.txt
```

Paste the following base structure into that file **before collecting any data**:

```
==============================
SYSTEM OVERVIEW — SYSTEMINFO
==============================

==============================
CPU INFORMATION — CIM
==============================

==============================
MEMORY INFORMATION — CIM
==============================

==============================
MOTHERBOARD INFORMATION — CIM
==============================

==============================
BIOS INFORMATION — CIM
==============================

==============================
STORAGE PERFORMANCE — WINSAT DISK
==============================

==============================
NETWORK CONFIGURATION — IPCONFIG
==============================
```

All text-based outputs are written **directly into this file under their matching section**.

Screenshots are saved externally in `PC_DIAGNOSTICS_RAW`.

Use **Windows PowerShell (Run as Administrator)** for all commands.

---

## PART C — DATA COLLECTION (ALL STEPS ARE MANDATORY)

### 1️⃣ SYSTEM OVERVIEW — SYSTEMINFO

Run:

```
systeminfo
```

Action:

• Select **all output**
• Copy
• Paste under:

```
SYSTEM OVERVIEW — SYSTEMINFO
```

---

### 2️⃣ CPU INFORMATION — CIM

Run:

```
Get-CimInstance Win32_Processor |
Select-Object Name, NumberOfCores, NumberOfLogicalProcessors, MaxClockSpeed
```

Action:

• Copy output
• Paste under:

```
CPU INFORMATION — CIM
```

---

### 3️⃣ MEMORY INFORMATION — CIM

Run:

```
Get-CimInstance Win32_PhysicalMemory |
Select-Object Capacity, Speed, Manufacturer, PartNumber
```

Action:

• Copy output
• Paste under:

```
MEMORY INFORMATION — CIM
```

---

### 4️⃣ MOTHERBOARD INFORMATION — CIM

Run:

```
Get-CimInstance Win32_BaseBoard |
Select-Object Manufacturer, Product
```

Action:

• Copy output
• Paste under:

```
MOTHERBOARD INFORMATION — CIM
```

---

### 5️⃣ BIOS INFORMATION — CIM

Run:

```
Get-CimInstance Win32_BIOS |
Select-Object SMBIOSBIOSVersion, ReleaseDate
```

Action:

• Copy output
• Paste under:

```
BIOS INFORMATION — CIM
```

---

### 6️⃣ GPU INFORMATION — DXDIAG

Press **Win + R**, type:

```
dxdiag
```

Action:

• **Wait 10–30 seconds** for dxdiag to fully load (it may appear unresponsive — this is normal)
• Click **Save All Information**
• Save as:

```
dxdiag.txt
```

Location:

```
PC_DIAGNOSTICS_RAW\dxdiag.txt
```

No need to paste dxdiag text into the master file, the file is automatically made.

---

### 7️⃣ GPU THERMALS & USAGE — TASK MANAGER

Action:

• Open **Task Manager → Performance → GPU**
• Capture a **clear screenshot** showing temperature and usage
• Save inside `PC_DIAGNOSTICS_RAW`
• Name clearly (e.g. `GPU_TaskManager.png`)

---

### 8️⃣ STORAGE HEALTH — CRYSTALDISKINFO

Install **CrystalDiskInfo**.

For **each detected drive (arrows on the side)**:

• Capture a **full-window screenshot** showing drive model, health %, power‑on hours, and host writes
• Save screenshots inside `PC_DIAGNOSTICS_RAW`
• Name clearly (e.g. `Disk0_CrystalDiskInfo.png`, `Disk1_CrystalDiskInfo.png`)

---

### 9️⃣ STORAGE PERFORMANCE — WINSAT DISK

Run:

```
winsat disk
```

Action:

• Copy **all output**
• Paste under:

```
STORAGE PERFORMANCE — WINSAT DISK
```

---

### 🔟 NETWORK CONFIGURATION — IPCONFIG

Run:

```
ipconfig /all
```

Action:

• Copy **all output**
• Paste under:

```
NETWORK CONFIGURATION — IPCONFIG
```

---

## PART D — CHATGPT FINAL OUTPUT FORMAT (UNCHANGED)

After data collection, ChatGPT MUST generate the **final diagnostic report** using the **exact format defined in the reference document**.

ONLY values may change.
**All text, spacing, emojis, bullets, order, and separators remain IDENTICAL.**

This is the format, if you want a message send the following with the format below it:

(optional message): 
```
Please use these files and the format below to create an all-in-one specs file for my PC.
```

Format:

```
================== FULL SYSTEM DIAGNOSTIC & CHATGPT EVALUATION ==================
🗓 Report Generated On: <YYYY-MM-DD HH:MM:SS>

📑 Table of Contents:
1.	System Overview
2.	CPU, RAM, Motherboard, and BIOS
3.	Graphics (GPU) Subsystem
4.	Storage Devices and SMART Analysis
5.	Network Configuration
6.	ChatGPT Evaluation Summary
7.	Recommendations
8.	Final Verdict
===============================================================================
1.	SYSTEM OVERVIEW
===============================================================================
🖥️ System Host Information:
⦁	Host Name           : <VALUE>
⦁	Operating System    : <VALUE>
⦁	Installed Date      : <VALUE>
⦁	Last Boot Time      : <VALUE>
⦁	Time Zone / Locale  : <VALUE>
===============================================================================
2. CPU, RAM, MOTHERBOARD, AND BIOS
🧠 Processor (CPU):
⦁	Model               : <VALUE>
⦁	Cores / Threads     : <VALUE>
⦁	Base Frequency      : <VALUE>
⦁	Max Boost Observed  : <VALUE>
⦁	Virtualization      : <VALUE>
⦁	VM Monitor Extensions: <VALUE>
⦁	Average Utilization : <VALUE>
⦁	Temperature Range   : <VALUE>
💾 Memory (RAM):
⦁	Total Installed     : <VALUE>
⦁	In Use              : <VALUE>
⦁	Available           : <VALUE>
⦁	Virtual Memory Total: <VALUE>
⦁	Paging File         : <VALUE>
🧰 Motherboard and BIOS:
⦁	Model               : <VALUE>
⦁	BIOS Version        : <VALUE>
⦁	Secure Boot         : <VALUE>
⦁	TPM/PTT             : <VALUE>
===============================================================================
3. GRAPHICS (GPU) SUBSYSTEM
🎮 Primary GPU — <GPU NAME>:
⦁	VRAM (Dedicated)    : <VALUE>
⦁	VRAM (Shared)       : <VALUE>
⦁	Driver Version      : <VALUE>
⦁	Temperature         : <VALUE>
⦁	Load at Capture     : <VALUE>
⦁	Display             : <VALUE>
🎨 Secondary GPU — <GPU NAME>:
⦁	Driver Version      : <VALUE>
⦁	Temperature         : <VALUE>
⦁	Usage               : <VALUE>
===============================================================================
4. STORAGE DEVICES & SMART MONITORING
📦 [<LETTER>:] <DRIVE MODEL>:
⦁	Capacity            : <VALUE>
⦁	Free Space          : <VALUE>
⦁	Health              : <VALUE>
⦁	Power-On Hours      : <VALUE>
⦁	Host Writes         : <VALUE>
⦁	WinSAT Benchmark:
⦁	Seq Read / Write  : <VALUE>
⦁	Random Read       : <VALUE>
⦁	Latency            : <VALUE>
📌 Summary:
⦁	<Drive usage summary>
===============================================================================
5. NETWORK CONFIGURATION
🌐 Ethernet Controller:
⦁	Adapter             : <VALUE>
⦁	IP Address          : <VALUE>
⦁	Driver Version      : <VALUE>
⦁	Status              : <VALUE>
===============================================================================
6. CHATGPT EVALUATION SUMMARY
✅ Summary Points:
⦁	<POINT>
⦁	<POINT>
⦁	<POINT>
===============================================================================
7. RECOMMENDATIONS
⚠️ Action Items:
1.	<ITEM TITLE>
⦁	<DETAIL>
===============================================================================
8. FINAL VERDICT
🟢 SYSTEM STATUS: <STATUS>
<One-paragraph verdict>
Diagnostics verified with:
⦁	SystemInfo
⦁	DxDiag
⦁	CrystalDiskInfo
⦁	WinSAT
⦁	Manual inspection
===============================================================================
Report compiled by: ChatGPT (OpenAI) on <DATE>
```
