# TOTK Android UltraCam Ports

Android packages for **MaxLastBreath's UltraCam 2.7.1 and UltraCam Calamity 3.0.0** for *The Legend of Zelda: Tears of the Kingdom* in Eden. I configured, packaged, tested, and documented these presets. I did not create UltraCam; the original software is by [MaxLastBreath](https://github.com/MaxLastBreath/nx-optimizer).

**[Download the 900p Docked release](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/tag/v1.1.0-900p-docked)** · **[Download the 720p release](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/tag/v1.0.0-android-ports)** · **[Installation Guide — Read This First](#installation-guide--read-this-first)**

> **IMPORTANT: THIS IS THE 900P DOCKED PRESET. ENABLE DOCKED MODE IN EDEN BEFORE PLAYING.**

## 720p versus 900p

| Preset | Intended use | Target | Mode | UltraCam | Supplied shadow value |
| --- | --- | --- | --- | --- | ---: |
| **900p Docked v1.1.0** | Higher image quality | 1600 × 900 | **Docked** | 3.0.0 | `512` |
| **720p v1.0.0** | Higher performance | 1280 × 720 | Existing published setup | 2.7.1 or 3.0.0 | See its configuration |

The 900p preset retains `FSR = True`, `FXAA = False`, a 5000 render distance, FOV 45, Dynamic FPS, a 60 FPS target, and the tested shader and time-speed values. Its higher pixel count and `ShadowResolution = 512` can increase GPU load and memory use. The value `512` is the actual supplied setting; this release does not claim to use UltraCam's historical 8192 maximum.

The supplied handheld section remains:

```ini
[Handheld]
Width = 1280
Height = 720
OverrideHandheld_Resolution = False
```

I preserved these values. This release prioritizes Docked Mode and does not promise that changing Eden modes automatically changes UltraCam's internal resolution.

## Downloads

### 900p Docked — v1.1.0

| Asset | Install method |
| --- | --- |
| [`totk-ultracam-3.0.0-900p-docked-exefs-v1.1.0.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.1.0-900p-docked/totk-ultracam-3.0.0-900p-docked-exefs-v1.1.0.zip) | Install through TOTK **Add-ons**. |
| [`totk-ultracam-3.0.0-900p-docked-config-v1.1.0.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.1.0-900p-docked/totk-ultracam-3.0.0-900p-docked-config-v1.1.0.zip) | Extract into Eden's virtual **`sdmc`** root. |
| [`totk-eden-stable-900p-docked-v1.1.0.ini`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.1.0-900p-docked/totk-eden-stable-900p-docked-v1.1.0.ini) | Import through Eden Stable's per-game **Import Config** action. |

### 720p — v1.0.0

| Asset | Purpose |
| --- | --- |
| [`totk-ultracam-2.7.1-eden-720p.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/totk-ultracam-2.7.1-eden-720p.zip) | UltraCam 2.7.1 ExeFS add-on. |
| [`totk-ultracam-3.0.0-eden-720p.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/totk-ultracam-3.0.0-eden-720p.zip) | UltraCam 3.0.0 ExeFS add-on. |
| [`ULTRACAM.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/ULTRACAM.zip) | UltraCam 3.0.0 720p virtual-SD configuration. |
| [`regular.Eden.totk.ini`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/regular.Eden.totk.ini) | Existing Standard Eden per-game preset. |
| [`Nightly.Eden.Totk.ini`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/Nightly.Eden.Totk.ini) | Existing Eden Nightly per-game preset. |

The old README referred to pre-release filenames that were not present on GitHub. The table above uses the actual published v1.0.0 asset names.

## Game-version compatibility

**Use UltraCam 3.0.0 for TOTK 1.4.1 or 1.4.2.** These are my Android observations and are separate from upstream compatibility metadata.

| TOTK version | UltraCam 2.7.1 | UltraCam 3.0.0 |
| --- | --- | --- |
| 1.0.0 base game | 60 FPS unlock worked in my testing; not upstream-listed | Worked in my testing; not upstream-listed |
| 1.1.0–1.2.1 | Officially listed upstream | Officially listed upstream |
| 1.4.0 | Outside official 2.7.1 support | Officially listed upstream |
| 1.4.1–1.4.2 | Graphics changes loaded, but FPS remained around 30 in my tests | **Recommended; FPS unlock worked in my tests** |
| 1.4.3 | Repeated crashes in my Android setup | Repeated crashes in my Android setup |

The 1.4.3 result is device-specific and does not prove a universal incompatibility. See [compatibility details](docs/compatibility.md).

<a id="installation-guide--read-this-first"></a>

# Installation Guide — Read This First

The release contains three different file types. They are not interchangeable:

1. **UltraCam ExeFS package** — installed through TOTK's Eden **Add-ons** manager.
2. **UltraCam configuration** — for UltraCam 3.0.0, extracted into Eden's virtual **`sdmc`** storage using Android file access or Eden's supported user-data interface.
3. **Eden Stable INI** — imported through Eden's per-game **Import Config** action.

Back up your current per-game settings and `sdmc/UltraCam/TOTK/Config` files first. Disable conflicting UltraCam, Dynamic FPS, FPS, resolution, `main.npdm`, and `subsdk3` mods. **Enable only one UltraCam executable version at a time.**

## 1. Download the 900p files

Download all three assets from [v1.1.0-900p-docked](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/tag/v1.1.0-900p-docked):

1. [`totk-ultracam-3.0.0-900p-docked-exefs-v1.1.0.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.1.0-900p-docked/totk-ultracam-3.0.0-900p-docked-exefs-v1.1.0.zip)
2. [`totk-ultracam-3.0.0-900p-docked-config-v1.1.0.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.1.0-900p-docked/totk-ultracam-3.0.0-900p-docked-config-v1.1.0.zip)
3. [`totk-eden-stable-900p-docked-v1.1.0.ini`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.1.0-900p-docked/totk-eden-stable-900p-docked-v1.1.0.ini)

The ExeFS and configuration ZIPs are separate because Eden loads the executable as a game add-on while UltraCam reads its settings from the virtual SD card.

## 2. Install the UltraCam 3.0.0 ExeFS add-on

1. Open Eden Stable.
2. Locate *The Legend of Zelda: Tears of the Kingdom*.
3. Open the game's properties.
4. Select **Add-ons**.
5. Use the available install or import action.
6. Select the ExeFS ZIP, or its extracted `UltraCam 3.0.0` folder if your Eden build requires an unpacked folder.
7. Confirm that UltraCam 3.0.0 appears in the Add-ons list.
8. Enable it and disable UltraCam 2.7.1 or any conflicting FPS modification.

The effective structure must be:

```text
UltraCam 3.0.0/
└── exefs/
    ├── main.npdm
    └── subsdk3
```

**Install the ExeFS add-on through the game's Add-ons system. Do not copy it into the virtual SD-card configuration directory.**

## 3. Install the separate 900p UltraCam configuration

1. Use Android's file manager with the access already granted to Eden, or Eden's supported Files/user-data access interface.
2. Locate Eden Stable's existing virtual SD-card root, named **`sdmc`**. Its absolute Android path varies by build and device, so do not create a guessed path.
3. Open `totk-ultracam-3.0.0-900p-docked-config-v1.1.0.zip`.
4. Extract the included `UltraCam` folder **directly into the existing `sdmc` root**.
5. Allow replacement of the two configuration files only after backing up any customized versions.
6. Confirm the final paths below.

```text
sdmc/
└── UltraCam/
    └── TOTK/
        └── Config/
            ├── maxlastbreath.ini
            └── PaletteCFG.json
```

The required INI path is:

```text
sdmc/UltraCam/TOTK/Config/maxlastbreath.ini
```

**Do not install this configuration ZIP through Add-ons. Do not place it beside `main.npdm` or `subsdk3`.**

These duplicated paths are incorrect:

```text
sdmc/sdmc/UltraCam/TOTK/Config/
sdmc/UltraCam/UltraCam/TOTK/Config/
```

If the 720p configuration is already installed, copy its `maxlastbreath.ini` and `PaletteCFG.json` somewhere safe before replacing them. Restoring those files returns UltraCam to that saved configuration.

## 4. Enable Docked Mode

1. Open TOTK's per-game settings in Eden Stable.
2. Find the setting that controls Handheld/Docked mode. Exact wording may vary by Eden build.
3. Select **Docked Mode**.
4. Save the setting and restart the game or emulator if required.
5. Verify that the UltraCam configuration reports 1600 × 900.

**Without Docked Mode, do not assume the advertised 900p preset is active.** The INI intentionally leaves `OverrideHandheld_Resolution = False`.

## 5. Import the Eden Stable preset

The release INI is an Eden per-game configuration. It is not UltraCam's `maxlastbreath.ini`.

1. Back up your current TOTK per-game settings.
2. Download `totk-eden-stable-900p-docked-v1.1.0.ini`.
3. Open Eden Stable and locate TOTK.
4. Open the game's settings or properties.
5. Use the supported **Import Config** action.
6. Select the downloaded INI and confirm the import.
7. Review the imported CPU, renderer, resolution, and other values.
8. Verify that **Docked Mode** is selected.
9. Install and select a GPU driver compatible with your own GPU.
10. Restart Eden.

The exported preset contains a device-specific GPU-driver path for my Snapdragon 8 Gen 2 setup. Importing it does not install that driver, and the saved path can be invalid on another device. Select your own compatible driver after importing.

Some frame-generation fields remain in the exported configuration, but Standard Eden builds may not expose or support every Nightly-specific feature. Review the values that your build actually presents. Do not treat retained keys as proof that frame generation is active.

The corrected Stable preset is based on my supplied `EDEN STABLE SETTINGS.ini`. I enabled Docked Mode in the published copy while preserving its updated `scaling_filter = 0` choice and all other settings. The same corrected base settings are also published under a separate BOTW filename at my direction. Eden's exported INI format does not embed a Nintendo title ID, so the game-specific filenames identify where each copy is intended to be imported.

## 6. GPU driver information

My tested hardware is an **AYN Thor Max with Snapdragon 8 Gen 2 / Adreno 740**. The new Stable preset references `Balemuni_Apex_v2_ULTIMATE_SD8Gen2.zip` on my device. This repository does not redistribute that driver.

To use a custom driver:

1. Download a driver package compatible with your GPU and Eden build from its original publisher.
2. Open Eden's **GPU Driver Manager**.
3. Install the driver ZIP.
4. Select it for TOTK.
5. Restart Eden if required, then test stability, rendering, and frame pacing.

Previously documented options include [TurnipZ 0.3.0](https://github.com/AlexSanz0902/turnip-sd865-z/releases/tag/v0.3.0) and [Turnip v27.0.0-R1](https://github.com/StevenMXZ/Adreno-Tools-Drivers/releases/tag/v27.0.0-R1). My smoother-gameplay comment about the newer release was qualitative and was not a measured FPS improvement. See [GPU-driver notes](docs/gpu-drivers.md).

## 7. Verify the installation

1. Completely restart Eden Stable.
2. Launch TOTK and confirm that it loads normally.
3. With UltraCam 3.0.0, hold **ZL + ZR**, then press **L3** to open the performance menu in my tested controller setup.
4. Verify `Width = 1600`, `Height = 900`, `ShadowResolution = 512`, `MaxFPS = 60`, and Dynamic FPS enabled.
5. Confirm that Docked Mode is active.
6. Confirm that Link moves at normal speed.
7. Check for missing textures, graphical artifacts, flicker, and shadow problems.
8. Test an overworld area and a shrine.

The UltraCam menu appearing proves that the executable loaded; it does not by itself prove that the correct INI loaded. Compare the displayed values with the 900p configuration.

## 8. UltraCam 2.7.1 and the 720p release

The 900p release recommends UltraCam 3.0.0. The historical 2.7.1 package contains ExeFS files only and is installed through Add-ons:

```text
UltraCam 2.7.1/
└── exefs/
    ├── main.npdm
    └── subsdk3
```

UltraCam 2.7.1's legacy configuration path is `romfs/UltraCam/maxlastbreath.ini`, but that legacy RomFS configuration is not included in the v1.0.0 2.7.1 package. Do not give 2.7.1 the UltraCam 3.0.0 SDMC configuration. On TOTK 1.4.1 and 1.4.2, I observed its graphics changes working while the FPS unlock remained around 30; use 3.0.0 for those updates.

## 9. Troubleshooting

- **UltraCam does not load:** make sure `exefs` is directly under the enabled add-on folder, confirm `main.npdm` and `subsdk3` are present, disable conflicts, and restart Eden.
- **UltraCam loads but ignores the 900p settings:** verify `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini`; remove duplicated `sdmc` or `UltraCam` folders.
- **The game runs in slow motion:** check Dynamic FPS, time-speed values, Eden's emulation-speed setting, and conflicting FPS modifications.
- **The display remains at a handheld profile:** enable Docked Mode and restart the game. The preset does not enable handheld-resolution override.
- **Imported INI cannot find the GPU driver:** install a compatible driver and select it manually. A saved path from another Android device does not install a driver.
- **Frame generation is missing:** the Stable build may not expose that Nightly feature. The 900p results below do not depend on a guarantee that frame generation is present.
- **UltraCam 2.7.1 stays near 30 FPS on 1.4.1/1.4.2:** this matches my observed limitation; use UltraCam 3.0.0.
- **TOTK 1.4.3 crashes:** I experienced repeated crashes on my setup. This is an observation, not a universal claim.
- **Graphics are corrupted or stability worsens:** return to a known-working driver, disable conflicting mods, and restore your backed-up configuration.

See [detailed installation notes](docs/installation.md) and [troubleshooting](docs/troubleshooting.md).

## 900p performance and visual-quality notes

I tested the 900p Docked preset on my **AYN Thor Max with Snapdragon 8 Gen 2 / Adreno 740**. Compared with my 720p configuration, I observed approximately **5 FPS lower performance in comparable overworld gameplay**, while shrines still reached approximately **60 FPS**. These are my reported observations, not independently reproduced benchmarks or universal results.

The test presents a quality-versus-performance trade-off. It does not establish that the difference is caused exclusively by resolution or shadows, and it does not guarantee sustained native 60 FPS. Device, emulator build, GPU driver, scene, temperature, and measurement method can change the result.

## New Performance Findings — Standard Eden vs Eden Nightly

My earlier 720p comparison on the same class of hardware produced these displayed readings:

| Emulator build | UltraCam | Resolution | Frame generation | Overworld | Shrines |
| --- | --- | --- | --- | ---: | ---: |
| **Standard Eden** | 3.0.0 | 1280 × 720 | Disabled / unavailable | **~50 FPS** | **~60 FPS** |
| Eden Nightly — earlier observation | 3.0.0 | 1280 × 720 | Fixed 2× configured | ~40 FPS | ~55 FPS |

The arithmetic differences are about +25% and +9.1% in the displayed readings. This was not a controlled benchmark, and the Nightly counter's treatment of generated frames was not established. These figures do not prove an equivalent native-FPS gain or a confirmed Nightly regression. Standard Eden may be preferable on similar setups, but further testing is necessary. See [benchmark notes](docs/benchmarks.md).

## Credits and licensing

- **MaxLastBreath:** original NX Optimizer and UltraCam development.
- **MPDERPER:** Android configuration, adaptation, packaging, optimization, and testing.
- **ChatGPT:** technical and documentation assistance.

The unchanged UltraCam binaries are redistributed under the upstream **CC BY-NC 2.0** notice. See [licensing](LICENSING.md), [upstream notice](LICENSE.upstream.md), [credits](CREDITS.md), and [provenance](PROVENANCE.md). This unofficial project does not imply endorsement by Nintendo, Eden, or MaxLastBreath.

No ROM, game update, firmware, keys, emulator binary, GPU-driver binary, textures, models, music, screenshots, or other game assets are included.

## Disclaimer

Use these community packages at your own risk. Back up saves and configurations, monitor temperature and stability, and follow the laws and license terms that apply to you.
