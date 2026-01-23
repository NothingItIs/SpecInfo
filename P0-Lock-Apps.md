# 🛡️ GPU P0 LOCK TEST LOG (My System – RTX 3080)

Legend:
- YES = Locks GPU in P0 (bad, causes 1710 MHz idle bug)
- NO  = Does NOT lock GPU (safe, stays P8 ~200 MHz)
- ⚠️  = Conditional (safe only with correct settings)

---

| Application / Feature          | Locks P0? | Status | Notes |
|--------------------------------|-----------|--------|-------|
| Microsoft Edge                 | NO        | ✅ Safe | Tested idle → stays P8 |
| Task Manager                   | NO        | ✅ Safe | Never opens GPU context |
| Command Prompt / PowerShell    | NO        | ✅ Safe | Used with nvidia-smi |
| nvidia-smi                     | NO        | ✅ Safe | Diagnostic only |
|--------------------------------|-----------|---------|------------------------------|
| MSI Afterburner (main window)  | NO        | ✅ Safe | Overlay OFF, monitoring only |
| Wallpaper Engine (paused)      | NO        | ⚠️ Safe | Safe only when paused / static |
| Wallpaper Engine (animated)    | YES       | ❌ Bad  | 3D / video wallpapers can lock P0 |
|--------------------------------|-----------|---------|------------------------------|
| Opera GX (HW Accel OFF)        | NO        | ✅ Safe | Fixed — no longer locks GPU |
| Opera GX (HW Accel ON)         | YES       | ❌ Bad  | Previously locked GPU at 1710 MHz |
|--------------------------------|-----------|---------|------------------------------|
| NVIDIA Overlay                 | NO        | ✅ Safe | Tested, no P0 lock |
|--------------------------------|-----------|---------|------------------------------|
| Gigabyte Control Center (GCC)  | YES       | ❌ Bad  | Dynamic Lighting / monitoring caused P0 |
| GCC (services disabled)        | NO        | ✅ Fixed | After disabling modules, P8 works |
|--------------------------------|-----------|---------|------------------------------|
| Windows Update Services        | NO        | ✅ Safe | Not the cause in your case |
|--------------------------------|-----------|---------|------------------------------|
| ChatGPT (desktop / web)        | NO        | ✅ Safe | Does not open GPU context |
| Riot Client (HW accel OFF)     | NO        | ✅ Safe | Stays P8 when idle |
| Riot Client (HW accel ON)      | YES       | ❌ Bad  | P0 – Hardware acceleration on |
| VALORANT (running / menu)     | YES       | ❌ Bad  | Keeps GPU active while game is open (expected) |
|--------------------------------|-----------|---------|------------------------------|
| 3DMark (idle, no test)         | NO        | ✅ Safe | No usage at idle |
| 3DMark (running test)         | YES       | ❌ Bad  | Full load, expected P0 behavior |
|--------------------------------|-----------|---------|------------------------------|
| Razer Services (background)    | NO        | ✅ Safe | Normal services do not lock GPU |
| Razer App / RazerAppEngine.exe | YES       | ❌ Bad  | Opens GPU context, locks P0 |

---

## 🔍 HOW I VERIFY IDLE HEALTH

Command:
```
nvidia-smi
```