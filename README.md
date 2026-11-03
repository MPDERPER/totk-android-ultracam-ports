# TOTK Android UltraCam Ports

Community-maintained Android packages for **MaxLastBreath's UltraCam 2.7.1 and UltraCam Calamity 3.0.0**, prepared for *The Legend of Zelda: Tears of the Kingdom* in Eden Nightly with a 1280 × 720 target.

**[Download v1.0.0](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/tag/v1.0.0-android-ports)** · **[Complete installation guide](docs/installation.md)** · [Compatibility](docs/compatibility.md) · [GPU drivers](docs/gpu-drivers.md) · [Troubleshooting](docs/troubleshooting.md)

I manually adapted, configured, packaged, and tested these Android setups. **I did not create UltraCam.** The original UltraCam and NX Optimizer software was developed by [MaxLastBreath](https://github.com/MaxLastBreath/nx-optimizer). This is an unofficial community project.

## Downloads

| Asset | Purpose |
| --- | --- |
| [`totk-ultracam-2.7.1-eden-720p.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/totk-ultracam-2.7.1-eden-720p.zip) | UltraCam 2.7.1 ExeFS add-on. |
| [`totk-ultracam-3.0.0-eden-720p.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/totk-ultracam-3.0.0-eden-720p.zip) | UltraCam 3.0.0 ExeFS add-on. |
| [`totk-ultracam-3.0.0-android-config.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/totk-ultracam-3.0.0-android-config.zip) | UltraCam 3.0.0 virtual-SD configuration. |
| [`0100F2C0115B6000.ini`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/0100F2C0115B6000.ini) | Optional Eden Nightly per-game preset. |

Install **only one** UltraCam ExeFS version at a time. The ExeFS add-on, UltraCam configuration, and Eden per-game preset have different destinations.

## Important compatibility warning

**Use UltraCam 3.0.0 for TOTK 1.4.1 or 1.4.2.** In my Android testing, UltraCam 2.7.1 still loaded and applied graphics changes on those updates, including reduced render distance and modified FOV, but its FPS unlock did not work and gameplay remained around 30 FPS. On the unupdated 1.0.0 base game, I observed the 2.7.1 package running with its 60 FPS unlock working.

| TOTK version | UltraCam 2.7.1 | UltraCam 3.0.0 |
| --- | --- | --- |
| 1.0.0 — base game | 60 FPS unlock worked in my testing; not upstream-listed | Reported working in my testing; not upstream-listed |
| 1.1.0–1.2.1 | Officially listed upstream | Officially listed upstream |
| 1.4.0 | Outside official 2.7.1 support; not separately tested here | Officially listed upstream |
| 1.4.1 | **Partial:** graphics work, FPS remains around 30 | **Recommended:** FPS unlock works in my testing |
| 1.4.2 | **Partial:** graphics work, FPS remains around 30 | **Recommended:** FPS unlock works in my testing |
| 1.4.3 | Repeated crashes in my Android setup | Repeated crashes in my Android setup |

The 1.4.3 result is device-specific, not a universal incompatibility claim. Historical upstream support and my Android tests are separated in [Compatibility](docs/compatibility.md).

<a id="installation-guide-eden-nightly-android"></a>

# Installation Guide — Eden Nightly (Android)

This complete workflow keeps three different components separate:

- The **UltraCam ExeFS add-on** is installed for TOTK through Eden’s **Add-ons** interface.
- The **UltraCam 3.0.0 configuration** is extracted into Eden’s virtual **`sdmc`** root.
- The optional **Eden per-game preset** is imported with Eden’s **Import Config** function.

Choose either UltraCam 2.7.1 or UltraCam 3.0.0. **Never enable both executable versions at the same time.** Back up your current TOTK per-game settings and existing mods before continuing. Disable other UltraCam, Dynamic FPS, FPS, resolution, `main.npdm`, or `subsdk3` modifications that could conflict.

## 1. Download the required files

Download the files you need from the existing [v1.0.0 release](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/tag/v1.0.0-android-ports):

- **UltraCam 2.7.1:** [`totk-ultracam-2.7.1-eden-720p.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/totk-ultracam-2.7.1-eden-720p.zip)
- **UltraCam 3.0.0:** [`totk-ultracam-3.0.0-eden-720p.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/totk-ultracam-3.0.0-eden-720p.zip)
- **UltraCam 3.0.0 configuration:** [`totk-ultracam-3.0.0-android-config.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/totk-ultracam-3.0.0-android-config.zip)
- **Optional Eden Nightly settings preset:** [`0100F2C0115B6000.ini`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/0100F2C0115B6000.ini)

For 2.7.1, download the 2.7.1 ExeFS ZIP. For 3.0.0, download both the 3.0.0 ExeFS ZIP and its separate configuration ZIP. The Eden preset is optional for either version.

## 2. Install UltraCam 2.7.1

1. Download [`totk-ultracam-2.7.1-eden-720p.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/totk-ultracam-2.7.1-eden-720p.zip).
2. Open Eden Nightly on Android.
3. Locate *The Legend of Zelda: Tears of the Kingdom* in the game list.
4. Open the game’s properties.
5. Select **Add-ons**.
6. Use the available option to install or import an add-on.
7. Select the downloaded ZIP, or select its extracted mod folder if your Eden build requires an unpacked directory.
8. Confirm that UltraCam 2.7.1 appears in the Add-ons list.
9. Make sure the add-on is enabled, and make sure UltraCam 3.0.0 and conflicting FPS mods are disabled.
10. Fully restart TOTK. If the add-on does not initialize correctly, fully close and restart Eden Nightly as well.

The effective mod structure must contain:

```text
UltraCam 2.7.1/
└── exefs/
    ├── main.npdm
    └── subsdk3
```

This release contains the **UltraCam 2.7.1 ExeFS files only**. The original UltraCam 2.7.1 configuration system uses:

```text
romfs/UltraCam/maxlastbreath.ini
```

The published 2.7.1 package does not include that legacy RomFS configuration. The ExeFS-only package can still perform its built-in behavior; I observed it unlocking FPS on the base game. **Do not install the UltraCam 3.0.0 SDMC configuration for UltraCam 2.7.1.**

### UltraCam 2.7.1 version warning

- On my unupdated TOTK 1.0.0 base-game installation, UltraCam 2.7.1 successfully unlocked 60 FPS.
- On TOTK 1.4.1 and 1.4.2, it still applied graphical optimizations such as render-distance and FOV changes in my tests.
- Its FPS unlock did not work correctly on 1.4.1 or 1.4.2 in my tests, leaving gameplay capped at approximately 30 FPS.
- The original official 2.7.1 compatibility metadata lists TOTK 1.1.0 through 1.2.1.

These are my observed Android results, not universal guarantees. **I recommend UltraCam 3.0.0 for TOTK 1.4.1 and 1.4.2.**

## 3. Install UltraCam 3.0.0

UltraCam 3.0.0 requires two separate installation steps. The ExeFS add-on supplies the executable mod, while the SDMC configuration supplies UltraCam’s settings. Both are required for the published configuration to be applied.

### Step A — Install the ExeFS add-on

1. Download [`totk-ultracam-3.0.0-eden-720p.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/totk-ultracam-3.0.0-eden-720p.zip).
2. Open Eden Nightly and select TOTK.
3. Open the game’s properties.
4. Select **Add-ons**.
5. Import the UltraCam 3.0.0 executable mod, using the ZIP or extracted folder according to the options supported by your Eden build.
6. Confirm that the mod appears in the list and is enabled. Disable UltraCam 2.7.1 and any conflicting FPS or `subsdk3` mod.

The effective add-on structure must contain:

```text
UltraCam 3.0.0/
└── exefs/
    ├── main.npdm
    └── subsdk3
```

### Step B — Install the UltraCam 3.0.0 SDMC configuration

1. Download [`totk-ultracam-3.0.0-android-config.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/totk-ultracam-3.0.0-android-config.zip).
2. Locate Eden Nightly’s virtual SD-card root, named **`sdmc`**. Depending on your Android and Eden versions, use Android’s file manager with the storage access already granted to Eden, or use Eden’s supported user-data access or export interface. The exact Android location varies, so do not create a guessed storage path.
3. Open the configuration ZIP and find the included `UltraCam` directory.
4. Extract that `UltraCam` directory **directly inside the existing virtual `sdmc` root**.
5. Confirm that both configuration files exist at the final paths shown below.
6. Fully close and restart Eden Nightly after the files have been copied.

The final structure must be:

```text
Eden Nightly/
└── sdmc/
    └── UltraCam/
        └── TOTK/
            └── Config/
                ├── maxlastbreath.ini
                └── PaletteCFG.json
```

The required INI location is:

```text
sdmc/UltraCam/TOTK/Config/maxlastbreath.ini
```

**Do not install the configuration ZIP through the game’s Add-ons manager. Do not place the configuration beside `main.npdm` or `subsdk3`.** Eden loads the executable files through the game’s ExeFS add-on directory, while UltraCam reads its user configuration from the virtual SD card. That is why the two packages have different destinations.

Avoid these incorrect duplicated structures:

```text
sdmc/sdmc/UltraCam/TOTK/Config/
```

```text
sdmc/UltraCam/UltraCam/TOTK/Config/
```

## 4. Import the optional Eden Nightly settings preset

[`0100F2C0115B6000.ini`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/0100F2C0115B6000.ini) contains my **per-game Eden Nightly configuration**. It is not an UltraCam configuration file and must not replace `maxlastbreath.ini`.

**Importing this preset can overwrite existing TOTK per-game preferences. Back up your current configuration first.**

1. Download `0100F2C0115B6000.ini`.
2. Open Eden Nightly.
3. Locate TOTK in the game list.
4. Open the game’s properties.
5. Locate Eden’s supported **Import Config** option.
6. Select the downloaded `0100F2C0115B6000.ini` file.
7. Confirm the import.
8. Review the imported CPU, graphics, resolution, and frame-generation settings.
9. Verify that the correct GPU driver is selected for your device.
10. Fully restart Eden Nightly.

The exact position or name of the import control can vary between Eden builds. If **Import Config** is not visible, consult the interface or documentation for your installed build instead of manually copying the file into a guessed Android folder.

The preset contains an Android-specific path for the GPU driver used when it was exported. Importing the preset does not install that driver, and its saved path may not exist on another device. Install and select your own compatible GPU driver after importing when necessary.

## Recommended GPU Drivers

My tested device is the **AYN Thor Max with Snapdragon 8 Gen 2 and Adreno 740**.

- **Previous driver:** [TurnipZ 0.3.0](https://github.com/AlexSanz0902/turnip-sd865-z/releases/tag/v0.3.0). This is the driver associated with the original preset and published benchmark readings.
- **Newly tested driver:** [Turnip v27.0.0-R1](https://github.com/StevenMXZ/Adreno-Tools-Drivers/releases/tag/v27.0.0-R1) by StevenMXZ. I noticed smoother gameplay after using a driver from this release, but I did not record a new controlled benchmark or the exact ZIP selected. This is a qualitative observation, not a measured FPS improvement.

To install a custom driver:

1. Download a driver ZIP that is compatible with your GPU, Android environment, and Eden build.
2. Open Eden Nightly’s **GPU Driver Manager**.
3. Install or import the driver ZIP through that manager.
4. Select the installed driver for TOTK.
5. Restart Eden if required, then test rendering, stability, FPS, and frame pacing.

For Adreno 740, the regular `Turnip_v27.0.0-R1.zip` is the appropriate starting option, subject to the developer’s current compatibility guidance. The `Turnip_Gen8_V38` packages are intended for A8xx GPUs and are **not** the recommended starting point for Adreno 740. The OneUI archive is specialized for relevant Samsung environments. Keep a previously working driver available so you can switch back if necessary.

This repository does not bundle third-party GPU-driver binaries. Read the [GPU-driver guide](docs/gpu-drivers.md) for the documented compatibility limits.

## 5. Confirm the frame-generation settings

The supplied Eden preset uses:

```text
Frame Generation: Enabled
Mode: Fixed Multiplier
Multiplier: 2×
Frame Queue Target: Balanced
Motion Estimation Resolution: 50%
```

After importing the preset, open TOTK’s per-game settings and confirm these values. Interface labels may vary slightly by Eden build. Frame generation adds interpolated output frames; those frames are separate from native game-rendered FPS and can affect latency, visual quality, and FPS-counter behavior. **These settings do not guarantee 60 FPS gameplay.**

## 6. Verify that UltraCam is working

1. Completely close and restart Eden Nightly.
2. Launch TOTK and confirm that the game loads normally.
3. If using UltraCam 3.0.0, hold **ZL + ZR**, then press the left joystick (**L3**) to open the performance menu in my tested controller configuration.
4. Verify the configured resolution and FPS values shown in UltraCam.
5. Confirm that Link moves at normal speed rather than in slow motion.
6. Check for missing textures, graphical artifacts, flickering, and shadow problems.
7. Test gameplay in an overworld area.
8. Test gameplay inside a shrine.
9. Confirm that the selected GPU driver remains active after restarting Eden.

The UltraCam menu appearing does not automatically prove that the intended `maxlastbreath.ini` was loaded. Compare the displayed settings with the expected values and recheck the exact SDMC path if 3.0.0 appears to ignore the configuration.

## 7. Common installation mistakes

- Enabling UltraCam 2.7.1 and 3.0.0 simultaneously.
- Installing the 3.0.0 configuration ZIP through **Add-ons** instead of extracting it into `sdmc`.
- Placing `maxlastbreath.ini` beside the ExeFS files.
- Leaving the configuration ZIP unextracted.
- Creating `sdmc/sdmc/UltraCam/TOTK/Config/`.
- Creating `sdmc/UltraCam/UltraCam/TOTK/Config/`.
- Giving the 3.0.0 SDMC configuration to UltraCam 2.7.1.
- Leaving another UltraCam, Dynamic FPS, FPS, `main.npdm`, or `subsdk3` modification enabled.
- Treating `0100F2C0115B6000.ini` as the UltraCam INI.
- Assuming that importing the Eden preset also installs its referenced GPU driver.

## 8. Troubleshooting

- **UltraCam does not load:** confirm that `exefs` is directly under the selected add-on folder, verify that `main.npdm` and `subsdk3` are present, make sure the mod is enabled, disable conflicts, and fully restart Eden.
- **UltraCam 3.0.0 loads but ignores settings:** verify the exact `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini` filename and path. Remove duplicated `sdmc` or `UltraCam` folders and confirm that you edited the file Eden is actually exposing to UltraCam.
- **The game runs in slow motion:** check Dynamic FPS or time-speed settings, Eden’s emulation-speed setting, and other FPS modifications. Disable conflicts and test again at conservative settings.
- **UltraCam 2.7.1 remains around 30 FPS on TOTK 1.4.1 or 1.4.2:** this matches the limitation I observed even when its FOV and render-distance changes worked. Use UltraCam 3.0.0 for these updates.
- **TOTK 1.4.3 crashes:** I encountered repeated crashes with 1.4.3 in my Android setup. This does not establish that every emulator build, device, or UltraCam configuration will crash.
- **The imported Eden INI does not recognize the GPU driver:** install a driver compatible with your own GPU and select it manually through Eden’s GPU Driver Manager. A saved path from another device will not install the driver.
- **Frame generation does not work:** confirm that the Eden build and hardware support the feature, verify the imported settings, restart Eden, and test without conflicting graphics or FPS modifications.
- **Textures, shadows, or graphics are corrupted:** switch back to a known-working GPU driver, disable conflicting mods, and test the default or conservative graphics settings.

For additional reference, see the separate [installation notes](docs/installation.md) and [troubleshooting guide](docs/troubleshooting.md).

## UltraCam 2.7.1 versus 3.0.0

| | UltraCam 2.7.1 | UltraCam 3.0.0 |
| --- | --- | --- |
| Recommended use | Primarily older TOTK versions | Newer tested updates, especially 1.4.1 and 1.4.2 |
| ExeFS installation | Eden **Add-ons** | Eden **Add-ons** |
| Configuration system | Legacy `romfs/UltraCam/maxlastbreath.ini` | `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini` |
| Configuration supplied here | ExeFS only; legacy INI not included | Separate configuration ZIP included |
| 1.4.1/1.4.2 FPS unlock | Did not work in my tests | Worked in my tests |
| Verified menu shortcut | Not verified for this build | Hold **ZL + ZR**, then press **L3** |

The 2.7.1 ExeFS-only package can function without a separately supplied legacy INI; I observed its FPS unlock on the base game. The legacy RomFS file is the original customization path, not a guarantee that the old FPS patch works on 1.4.x. Do not give 2.7.1 the 3.0.0 SD-card INI.

## New Performance Findings — Standard Eden vs Eden Nightly

In my latest real-world test, **UltraCam 3.0.0 reached approximately 50 FPS in the overworld and 60 FPS in shrines at 1280 × 720** on an AYN Thor Max with Snapdragon 8 Gen 2 and Adreno 740. This test used **Standard Eden**, meaning the stable/main release rather than Eden Nightly. Frame generation was unavailable and not active in this Eden build, so the new readings are observed gameplay FPS without generated output frames.

| Emulator build | UltraCam | Resolution | Frame generation | Overworld | Shrines |
| --- | --- | --- | --- | ---: | ---: |
| **Standard Eden (stable/main)** | 3.0.0 | 1280 × 720 | **Disabled / unavailable** | **~50 FPS** | **~60 FPS** |
| Eden Nightly — previous observation | 3.0.0 | 1280 × 720 | Fixed 2× configured | ~40 FPS | ~55 FPS |

The reported-reading differences are approximately **+25% in the overworld** and **+9.1% in shrines** for Standard Eden. These percentages compare the displayed observations only. They do **not** prove native-FPS improvements of 25% or 9.1%, because this was not a controlled benchmark and the previous Nightly counter’s treatment of generated frames was never conclusively established.

Other settings were kept consistent with my previous configuration, including the FreeDeno settings, CPU configuration, UltraCam INI, and GPU-driver choice. The supplied Standard Eden INI still contains inherited frame-generation fields, but the feature was not available or active in the tested build; retained configuration keys are not evidence that generated frames were used.

Standard Eden delivered higher observed FPS in this test despite being updated less frequently than Nightly. This makes Standard Eden a **potentially preferable option for UltraCam 3.0.0 users on similar hardware**, but further testing is necessary. The result does not establish a Nightly performance regression or attribute the difference exclusively to UltraCam. Emulator implementation differences, CPU/GPU scheduling, Vulkan behavior, frame pacing, thermal state, caches, scene selection, and measurement methodology are possible explanations, not confirmed causes.

A future controlled comparison should use the same location, save file, GPU driver, 1280 × 720 resolution, FPS counter, device temperature conditions, and frame-generation state. No exact Standard Eden build number, test duration, 1% low, or frame-time capture was recorded for this observation. See [Reported performance](docs/benchmarks.md) for the complete context.

## Historical performance observations — Eden Nightly

The earlier readings below remain preserved as historical observations from the **TurnipZ 0.3.0 configuration on Eden Nightly**, not Turnip v27.0.0-R1:

| Location | UltraCam 2.7.1 | UltraCam 3.0.0 | Relative difference |
| --- | ---: | ---: | ---: |
| Overworld | 35 FPS | 40 FPS | +14.29% |
| Shrines | 45 FPS | 55 FPS | +22.22% |

They are my observed readings, not independently reproduced benchmarks or guaranteed sustained rates. Fixed 2× frame generation was configured, and the supplied material does not establish whether the counter included generated frames. My later “smoother” Turnip v27.0.0-R1 report is qualitative and does not prove higher average FPS, 1% lows, or a specific mechanism. See [Reported performance](docs/benchmarks.md).

## Credits and licensing

- **MaxLastBreath:** original NX Optimizer and UltraCam development.
- **MPDERPER:** Android adaptation, configuration, troubleshooting, testing, and packaging.
- **StevenMXZ:** Adreno-Tools-Drivers and the linked Turnip v27.0.0-R1 release.
- **ChatGPT:** technical assistance with validation and documentation.

The unchanged UltraCam binaries are redistributed under MaxLastBreath’s published **CC BY-NC 2.0** notice. No ROM, update, firmware, keys, emulator binary, or GPU-driver binary is included. See [LICENSING.md](LICENSING.md), [CREDITS.md](CREDITS.md), and [PROVENANCE.md](PROVENANCE.md).

## Disclaimer

This project is not affiliated with or endorsed by MaxLastBreath, Nintendo, Eden, StevenMXZ, or the TurnipZ developers. Use legally obtained game content. Back up your data. Results vary by hardware, driver, emulator build, game update, scene, mods, and thermal conditions.
