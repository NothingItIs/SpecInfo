# 🎮 NVIDIA Control Panel — Ultimate Gaming Profile (RTX 3080 + G‑SYNC)

This file contains the **exact recommended global NVIDIA Control Panel settings** for a high‑performance, low‑latency gaming system.

System profile target:

* GPU: RTX 3080
* Monitor: G‑SYNC Compatible
* Goal: Max FPS, lowest latency, full stability

---

## 📂 Location

Open:
NVIDIA Control Panel → Manage 3D Settings → **Global Settings**

(We will later add per‑game profiles if needed.)

---

## ⚙️ GLOBAL SETTINGS (ALPHABETICAL ORDER)

### Image Scaling

**Off**

### Ambient Occlusion

**Off**

### Anisotropic Filtering

**Application‑controlled**

### Antialiasing – FXAA

**Off**

### Antialiasing – Gamma Correction

**On**

### Antialiasing – Mode

**Application‑controlled**

### Antialiasing – Setting

**Application‑controlled**

### Antialiasing – Transparency

**Off**

---

### Background Application Max Frame Rate

**Off** (or 30 if you want quiet background apps)

---

### CUDA – GPUs

**All**

### CUDA – Sysmem Fallback Policy

**Driver Default**

---

### DSR – Factors

**Off**

### DSR – Smoothness

**Off**

---

### Low Latency Mode

**Off**
(We will use NVIDIA Reflex inside games instead — better and safer)

---

### Max Frame Rate

**Off**
(Frame limiting will be done via RTSS or in‑game if needed)

---

### Monitor Technology

**G‑SYNC Compatible**

---

### Multi‑Frame Sampled AA (MFAA)

**Off**

---

### OpenGL GDI Compatibility

**Auto**

---

### OpenGL Rendering GPU

**NVIDIA GeForce RTX 3080**

---

### Power Management Mode

**Prefer Maximum Performance**  🔥

---

### Preferred Refresh Rate

**Highest Available**

---

### Shader Cache Size

**Unlimited**

---

### Texture Filtering – Anisotropic Sample Optimization

**On**

### Texture Filtering – Negative LOD Bias

**Allow**

### Texture Filtering – Quality

**High Performance**

### Texture Filtering – Trilinear Optimization

**On**

---

### Threaded Optimization

**On**

---

### Triple Buffering

**Off**

---

### Vertical Sync

**On**
(Important for proper G‑SYNC behavior — we will cap FPS separately)

---

### Virtual Reality – Pre‑Rendered Frames

**1**

### Virtual Reality – Variable Rate Super Sampling

**Off**

---

### Vulkan / OpenGL Present Method

**Auto**

---

## 🟢 G‑SYNC CONFIGURATION

Go to:
Display → Set up G‑SYNC

Settings:

* ☑️ Enable G‑SYNC, G‑SYNC Compatible
* 🔘 Enable for **Full Screen mode** (recommended for stability)
* ☑️ Enable settings for the selected display model

---

## 🧠 IMPORTANT NOTES

### Why V‑Sync = ON in Control Panel?

With G‑SYNC:

* NVCP V‑Sync ON = tear‑free safety net
* FPS must be capped slightly below refresh rate

Later we will:

* Add an FPS cap (Refresh‑3 rule, e.g. 162 for 165Hz)

---

### Low Latency Mode

We keep this OFF because:

* NVIDIA Reflex (in‑game) is better
* Avoids driver queue instability

---

## 🚀 NEXT PHASE AFTER THIS FILE

After applying these settings, we will:

1️⃣ Re‑run Steel Nomad with:

* Stock GPU
* 1905 @ 900 mV
* 1860 @ 875 mV

2️⃣ Compare:

* FPS
* Stability
* Latency

3️⃣ Lock final gaming profile 😈🔥

---

## ✅ STATUS

This profile is:

* Competitive‑gaming safe
* Benchmark‑stable
* Streaming‑safe
* Coding / dev‑safe

Nothing here affects VS Code, compilers, or development tools.

---

End of file.
