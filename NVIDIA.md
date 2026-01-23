# 🎮 NVIDIA Control Panel — Ultimate Gaming Profile (Global Settings)

> Rule used:
>
> * If the recommended value is the same as NVIDIA default → **Keep Default**
> * If different → I explicitly tell you what to change it to and why

---

## 🔹 3D Settings (Manage 3D Settings → Global Settings)

| Setting                               | Recommendation                            | Notes                                   |
| ------------------------------------- | ----------------------------------------- | --------------------------------------- |
| Image Scaling                         | **Keep Default (Off)**                    | Upscaling handled better in-game / DLSS |
| Ambient Occlusion                     | **Keep Default (Off)**                    | Game-controlled is better               |
| Anisotropic filtering                 | **Keep Default (Application-controlled)** | Let the game decide                     |
| Antialiasing – FXAA                   | **Keep Default (Off)**                    | Avoid blur                              |
| Antialiasing – Gamma correction       | **Keep Default (On)**                     | Correct gamma handling                  |
| Antialiasing – Mode                   | **Keep Default (Application-controlled)** | Game handles AA                         |
| Antialiasing – Setting                | **Keep Default (Application-controlled)** | Game handles AA                         |
| Antialiasing – Transparency           | **Keep Default (Off)**                    | Saves performance                       |
| Background Application Max Frame Rate | **Keep Default (Off)**                    | No background cap needed                |
| CUDA – GPUs                           | **Keep Default (All)**                    | Uses full GPU                           |
| CUDA – Sysmem Fallback Policy         | **Keep Default (Driver Default)**         | Safe                                    |
| DSR – Factors                         | **Keep Default (Off)**                    | No downsampling                         |
| DSR – Smoothness                      | **Keep Default (Off)**                    | Not used                                |
| Low Latency Mode | **Off** | Use NVIDIA Reflex inside games instead (better & safer) |
| Max Frame Rate | **Set to 162 FPS** | (For 165 Hz monitor → refresh −3 rule) |
| Monitor Technology | **Keep Default (G-SYNC Compatible)** | Correct |
| Multi-Frame Sampled AA (MFAA) | **Keep Default (Off)** | Not needed |
| OpenGL GDI compatibility | **Keep Default (Auto)** | Safe |
| OpenGL rendering GPU | **Keep Default (Auto-select)** | Correct GPU auto chosen |
| Power management mode | **Prefer maximum performance** | Prevents clock drops in games |
| Preferred refresh rate | **Keep Default (Highest available)** | Correct |
| Shader Cache Size | **Unlimited** | Reduces stutter & shader recompiles |
| Texture filtering – Anisotropic sample optimization | **Keep Default (Off)** | Quality-safe |
| Texture filtering – Negative LOD bias | **Clamp** | Prevents shimmering (important) |
| Texture filtering – Quality | **High performance** | Best FPS (no visible loss) |
| Texture filtering – Trilinear optimization | **Keep Default (On)** | Free performance |
| Threaded optimization | **On** | Improves CPU → GPU scheduling |
| Triple buffering | **Keep Default (Off)** | Only useful with V-Sync + OpenGL |
| Vertical sync | **On (in NVIDIA Control Panel)** | Correct for G-SYNC — turn OFF in-game |
| Virtual Reality pre-rendered frames | **Keep Default (1)** | Lowest latency |
| Virtual Reality – Variable Rate Supersampling | **Keep Default (Off)** | Not using VR |
| Vulkan/OpenGL present method | **Keep Default (Auto)** | Best compatibility |

---

## 🔹 G-SYNC Page (Set up G-SYNC)

* Enable G-SYNC, G-SYNC Compatible → ✅ Enabled
* Mode → **Enable for full screen mode only** (recommended for stability)
* Enable settings for selected display model → ✅ Enabled

---

## 🔹 In-Game Rules (VERY IMPORTANT)

When using this profile:

* In every game:

  * **V-Sync → OFF**
  * **NVIDIA Reflex → ON / ON + Boost** (if available)
  * Do NOT use in-game frame limiter (we already capped in driver)

---

## NVIDIA DRIVER PROFILES (IMPORTANT)

Instead of changing Global settings for every game, use **per-application profiles**.

This allows:
- Stable global baseline
- Competitive profiles for esports
- Benchmark profiles for 3DMark
- No conflicts between games

---

### HOW TO CREATE A PROFILE (NVIDIA CONTROL PANEL)

1. Open NVIDIA Control Panel  
2. Go to: Manage 3D Settings → Program Settings  
3. Click "Add" and select the game executable (.exe)  
4. Change settings ONLY for that game  
5. Click Apply  

These settings affect ONLY that game.

---

### COMPETITIVE GAME PROFILE (LOW LATENCY MODE)

Recommended for games like CS2 / Valorant / Apex / Fortnite:

- Low Latency Mode → ON (NOT Ultra)  

---

### SINGLE-PLAYER / AAA PROFILE (SMOOTH + STABLE)

Recommended for Cyberpunk / RDR2 / GTA / story games:

- Max Frame Rate → Off
- Power management mode → Normal
- Vertical Sync → Use 3D application setting

---

### BENCHMARK PROFILE (3DMARK / TESTING)

Recommended for 3DMark and stress tests:

- Max Frame Rate → Off
- Vertical Sync → Off
- Texture Filtering: Anisotropic sample optimization → On
- Texture Filtering - Negative LOD bias → Allow
- Texture Filtering - Quality → High Quality

---

## 🔹 Final Notes

This profile is tuned for:

* RTX 3080
* G-SYNC monitor (Pixio PXC277A)
* Low latency + maximum stability
* Best FPS without stutter or crashes
* Never mix aggressive settings in the Global profile.  
* Always use per-game profiles for tuning.

