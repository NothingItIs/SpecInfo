# How to Recreate a Full System Diagnostic File (Exact Format)

This tutorial walks you step‑by‑step through recreating **the exact same diagnostic file structure** for any PC (old or new), matching the layout, sections, tone, and depth of your existing report.

---

## PART A — What You Are Recreating

You are rebuilding a **consolidated diagnostic report** that merges:

* Windows system commands
* Built‑in diagnostic tools
* Third‑party hardware health tools
* Manual observations

All of this is then **normalized into one structured text file** with:

* Fixed section order
* Consistent labels
* Human‑readable explanations

---

## PART B — Data Collection (DO THIS FIRST)

Create a folder on the target PC called:

```
PC_DIAGNOSTICS_RAW
```

Everything you collect goes here.

### 1️⃣ System Overview

Open **Command Prompt (Admin)** and run:

```
systeminfo
```

* Select all output
* Copy → Paste into `systeminfo.txt`

Also note manually:

* PC name
* Windows edition
* Install date
* Time zone

---

### 2️⃣ CPU, RAM, Motherboard, BIOS

#### A. CPU + RAM

Run:

```
(Open PowerShell as Administrator)

Get-CimInstance Win32_Processor |
Select-Object Name, NumberOfCores, NumberOfLogicalProcessors, MaxClockSpeed

Get-CimInstance Win32_PhysicalMemory |
Select-Object Capacity, Speed, Manufacturer, PartNumber
```

Save as `cpu_ram.txt`

#### B. Motherboard + BIOS

Run:

```
wmic baseboard get product,manufacturer
wmic bios get smbiosbiosversion,releasedate
```

Save as `board_bios.txt`

---

### 3️⃣ GPU Information

Press **Win + R → dxdiag**

* Save All Information
* File name: `dxdiag.txt`

Optional (recommended):

* Screenshot GPU tab temperatures (Task Manager → Performance)

---

### 4️⃣ Storage + SMART Health

Install **CrystalDiskInfo**

* Take screenshots of **each drive**
* Note:

  * Health %
  * Power‑on hours
  * Host writes

Optional speed test:

```
winsat disk
```

Save output as `winsat.txt`

---

### 5️⃣ Network

Run:

```
ipconfig /all
```

Save as `network.txt`

---

## PART C — Assembly Phase (VERY IMPORTANT)

Now comes the part **you do with me**.

You will:

1. Send me:

   * The raw `.txt` files
   * Screenshots (GPU temps, CrystalDiskInfo)
2. Tell me:

   * Which PC this is ("Old Office PC", etc.)

I will:

* Normalize wording
* Calculate totals
* Remove noise
* Format into the **exact same report layout** you already have

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

## PART E — How to Repeat This for ANY PC

For a new PC:

1. Duplicate the `PC_DIAGNOSTICS_RAW` folder
2. Re‑run the same commands
3. Rename files only (content stays raw)
4. Send everything again

---

## PART F — What *I* Track Internally

When you send data, I internally:

* Cross‑validate temperatures
* Check driver sanity
* Flag aging storage
* Compare benchmarks vs expected baselines
* Detect misconfigurations (TPM, Secure Boot, VBS, etc.)

This ensures consistency across **all PCs you document**.

---

## PART G — Golden Rule

Never summarize or interpret the raw data yourself.
Always send it **unfiltered**.

That is how the reports stay identical and reliable.
