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
* Mode → Windowed and full screen (recommended for stability)
* Enable settings for selected display model → ✅ Enabled

---

## 🔹 PER-GAME NVIDIA DRIVER PROFILES (PERFORMANCE MODES)

> Rule used:
>
> * If a setting is NOT mentioned below → **Keep Global Defaults**
> * Only change the settings listed for that specific profile
> * Never modify Global profile for game-specific tuning

These profiles are designed to maximize **FPS, stability, and latency** depending on game type.

---

## ⚔️ FPS / COMPETITIVE PROFILE (MAX PERFORMANCE + LOW LATENCY)

Recommended for:
Valorant, CS2, Apex, Fortnite, Phasmophobia, Lethal Company, Minecraft PvP

Goal:
Lowest input latency, strongest 1% lows, highest competitive performance.

Change ONLY these settings in the game’s Program Profile:

| Setting             | Value | Notes |
| ------------------- | ----- | ----- |
| Low Latency Mode    | **On** | Use driver queue reduction (Reflex handles final latency) |
| Max Frame Rate      | **Off** | Let in-game limiter or Reflex control pacing |
| Vertical Sync       | **Off** | Prevents latency from driver V-Sync |

In-game rules:
- V-Sync → OFF  
- NVIDIA Reflex → **ON or ON + Boost**  
- Cap FPS in-game slightly below your stable maximum (example: 300 for Valorant)

This profile prioritizes:
⚡ Lowest input delay  
⚡ Best hit registration  
⚡ Strongest CPU thread scheduling  

---

## 🌄 OPEN-WORLD / AAA / SHADER PROFILE (SMOOTH + STABLE PERFORMANCE)

Recommended for:
Ghost of Tsushima, Watch Dogs, Cyberpunk, RDR2, Modded Minecraft (Shaders)

Goal:
Perfect frame pacing, zero tearing, stable clocks, smooth cinematic gameplay.

Change ONLY these settings in the game’s Program Profile:

| Setting                | Value | Notes |
| ---------------------- | ----- | ----- |
| Max Frame Rate         | **Off** | Let G-SYNC + driver pacing handle smoothness |
| Power management mode | **Normal** | Prevents unnecessary max clocks & heat in long sessions |
| Vertical Sync          | **Use 3D application setting** | Allows game / engine pacing control |

In-game rules:
- V-Sync → OFF  
- Use DLSS / FSR / Frame Gen if available  
- Let G-SYNC + driver V-Sync handle tearing prevention  

This profile prioritizes:
🌊 Smooth frametimes  
🌊 No tearing  
🌊 Stable clocks  
🌊 Best visual experience  

---

## 🧪 BENCHMARK / TESTING PROFILE (MAX RAW SCORE MODE)

Recommended for:
3DMark, stress tests, tuning validation

Goal:
Remove all limits and smoothing for maximum benchmark score.

Change ONLY these settings in the benchmark Program Profile:

| Setting                                    | Value |
| -----------------------------------------  | ----- |
| Max Frame Rate                             | **Off** |
| Texture filtering – Negative LOD bias      | **Allow** |
 |Texture filtering – Quality                | **High Quality**|
| Texture filtering – Trilinear optimisation | **On** |
| Vertical Sync                              | **Off** |

This profile prioritizes:
🔥 Highest possible FPS  
🔥 Maximum benchmark score  
🔥 No artificial caps or smoothing  

---

## 🔹 IMPORTANT NOTES

* If a setting is NOT listed above → **Keep Global Defaults**
* Always use per-game profiles — never mix aggressive settings into Global
* Competitive and AAA profiles can safely coexist
* Benchmark profile should ONLY be used for testing (not daily gaming)

---

## 🔹 Final Notes

This profile is tuned for:

* RTX 3080
* G-SYNC monitor (Pixio PXC277A)
* Low latency + maximum stability
* Best FPS without stutter or crashes
* Never mix aggressive settings in the Global profile.  
* Always use per-game profiles for tuning.

