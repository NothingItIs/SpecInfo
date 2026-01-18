# How to Recreate a Full System Diagnostic File (Exact Format)

This guide explains how to recreate **the exact same diagnostic file structure** for any PC (old or new), preserving the layout, section order, tone, and level of detail of the reference report.

---

## PART A — What You Are Recreating

You are rebuilding a **consolidated system diagnostic report** composed of:

* Windows system commands
* Built-in diagnostic tools
* Third-party hardware health tools
* Manual observations

These inputs are **normalized into a single structured text file** with:

* Fixed section order
* Consistent labels
* Human-readable explanations

---

## PART B — Data Collection (DO THIS FIRST)

Create a folder on the target PC named:

```
PC_DIAGNOSTICS_RAW
```

Use **Windows Powershell run as administrator** for all *Run* steps.

All collected data must be saved inside this folder.

---

### 1️⃣ System Overview

Run:

```
systeminfo
```

* Select all output
* Copy and paste into `systeminfo.txt`

Also record the following manually:

* PC name
* Windows edition
* Install date
* Time zone

---

### 2️⃣ CPU, RAM, Motherboard, BIOS

#### A. CPU + RAM

Run:

```
Get-CimInstance Win32_Processor |
Select-Object Name, NumberOfCores, NumberOfLogicalProcessors, MaxClockSpeed
```

```
Get-CimInstance Win32_PhysicalMemory |
Select-Object Capacity, Speed, Manufacturer, PartNumber
```

Save both outputs to:

```
cpu_ram.txt
```

---

#### B. Motherboard + BIOS

Run:

```
Get-CimInstance Win32_BaseBoard |
Select-Object Manufacturer, Product
```

```
Get-CimInstance Win32_BIOS |
Select-Object SMBIOSBIOSVersion, ReleaseDate
```

Save output to:

```
board_bios.txt
```

---

### 3️⃣ GPU Information

Press **Win + R**, type: (This might take upto a minuite to load, please wait.)

```
dxdiag
```

Press **Enter** and select **Save All Information**.

Save as:

```
dxdiag.txt
```

Optional (recommended):

* Screenshot GPU temperature data from Task Manager → Performance

---

### 4️⃣ Storage + SMART Health

Install **CrystalDiskInfo** and for each detected drive:

* Capture health percentage
* Capture power-on hours
* Capture host writes

Optional performance test:

```
winsat disk
```

Save output as:

```
winsat.txt
```

---

### 5️⃣ Network

Run:

```
ipconfig /all
```

Save output as:

```
network.txt
```

---

## PART D — Exact Section Order (DO NOT CHANGE)

1. System Overview
2. CPU, RAM, Motherboard, and BIOS
3. Graphics (GPU) Subsystem
4. Storage Devices and SMART Analysis
5. Network Configuration
6. ChatGPT Evaluation Summary
7. Recommendations
8. Final Verdict

---

## PART E — CHATGPT OUTPUT FORMAT (EXACT & NON-NEGOTIABLE)

ChatGPT MUST generate the final diagnostic file using the **exact formatting, section titles, emojis, bullet symbols, ordering, and separators** shown below.

ONLY values may change. **All text, symbols, emojis, spacing, and order must remain identical.**

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
