# Recommended GPU Drivers — Adreno 740

My AYN Thor Max uses Snapdragon 8 Gen 2 with Adreno 740. Custom-driver behavior varies by device, Android build, emulator version, workload, and shader state, so this page separates tested history from compatibility guidance.

## Driver history

| Driver | Status |
| --- | --- |
| [TurnipZ 0.3.0](https://github.com/AlexSanz0902/turnip-sd865-z/releases/tag/v0.3.0) | Previous tested configuration. It was used for the original benchmark readings, and its path remains in the released Eden preset. |
| [Turnip v27.0.0-R1](https://github.com/StevenMXZ/Adreno-Tools-Drivers/releases/tag/v27.0.0-R1) by StevenMXZ | Newly tested. I experienced smoother gameplay, but supplied no controlled measurements and did not record the exact selected ZIP. |
| Other drivers | Not established by this project. |

No GPU-driver binary is redistributed here.

## Choose the correct archive

| Archive | Guidance |
| --- | --- |
| `Turnip_v27.0.0-R1.zip` | Regular package and expected starting choice for Adreno 6xx/7xx, including Adreno 740, subject to current release metadata. |
| `Turnip_v27.0.0-R1-Oneui.zip` | Specialized OneUI option for relevant Samsung environments; not the AYN Thor Max default. |
| `Turnip_Gen8_V38.zip` | Official notes identify this V38 build for A8xx GPUs such as a840, a830, a829, a825, and a810. Not the default for Adreno 740. |
| `Turnip_Gen8_V38_Patched.zip` | Patched A8xx V38 variant; also not the Adreno 740 default. |

The official page proves that the archives exist and that the V38 builds target A8xx. It does not identify which archive I personally selected, so I do not present the regular archive as my confirmed tested file.

## Install in Eden Nightly

1. Open the official [StevenMXZ release](https://github.com/StevenMXZ/Adreno-Tools-Drivers/releases/tag/v27.0.0-R1).
2. Choose a package compatible with your GPU. For Adreno 740, start with the regular 6xx/7xx package unless current developer notes say otherwise.
3. Download the AdrenoTools-compatible ZIP.
4. Open Eden’s **GPU Driver Manager**, import/install the ZIP, and select it for TOTK.
5. Fully restart Eden when required.
6. Test stability, rendering correctness, average FPS, frame pacing, and shader behavior.
7. If results worsen, reselect the previous working driver or system/default driver and restart.

Do not extract or install systemwide components unless the developer explicitly instructs you to. Importing `0100F2C0115B6000.ini` does not install a driver and may restore the old TurnipZ path, so recheck the selected driver after importing.

## What “smoother” means here

My report is qualitative. It does not prove higher average FPS or a specific mechanism. Smoother presentation can involve consistent frame times, fewer visible stutters, different rendering behavior, shader compilation/cache differences, or Vulkan-workload compatibility, but I did not isolate those causes.

- **Average FPS:** average rendered frames per second over a measured interval.
- **1% lows:** a lower-percentile metric used to describe slower frame delivery.
- **Frame pacing:** consistency of frame delivery over time.
- **Frame generation:** interpolated output frames, distinct from native game-rendered frames.

No “stutter-free” claim or percentage improvement is made without measurements.
