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

## Quick Installation Guide

### UltraCam 2.7.1

1. Download `totk-ultracam-2.7.1-eden-720p.zip`.
2. In Eden Nightly, open TOTK’s properties and select **Add-ons**.
3. Import the package, enable it, and disable conflicting UltraCam, FPS, Dynamic FPS, `main.npdm`, or `subsdk3` mods.
4. Confirm the installed folder contains `exefs/main.npdm` and `exefs/subsdk3`, then fully restart Eden.
5. Prefer an older game version. On 1.4.1 and 1.4.2, expect graphics tweaks to load while the game remains around 30 FPS in my tested setup.

```text
UltraCam 2.7.1/
└── exefs/
    ├── main.npdm
    └── subsdk3
```

### UltraCam 3.0.0

1. Download `totk-ultracam-3.0.0-eden-720p.zip` and install it from TOTK’s **Add-ons** screen.
2. Download `totk-ultracam-3.0.0-android-config.zip` separately.
3. Extract the configuration ZIP into Eden Nightly’s **virtual SD-card root**. Do not install it through Add-ons.
4. Verify the final files are:

```text
sdmc/UltraCam/TOTK/Config/maxlastbreath.ini
sdmc/UltraCam/TOTK/Config/PaletteCFG.json
```

5. Fully restart Eden, launch TOTK, then hold **ZL + ZR** and click **L3** to open the tested controller menu.

Avoid `sdmc/sdmc/UltraCam`, `UltraCam/UltraCam/TOTK`, and leaving the configuration ZIP unextracted. Read the [complete installation guide](docs/installation.md) for precise layouts and verification steps.

## Importing the Eden Nightly preset

`0100F2C0115B6000.ini` is an optional **emulator per-game preset**, not UltraCam’s `maxlastbreath.ini`.

1. Back up your current TOTK per-game settings.
2. Open TOTK’s properties and use Eden’s supported **Import Config** action.
3. Import the file, review CPU and graphics settings, and reselect your GPU driver.
4. Restart Eden.

The preset preserves the original TurnipZ 0.3.0 path used for the earlier benchmark setup. Importing it does not install a driver, and its Android path may not exist elsewhere. It keeps 21,000 custom CPU ticks, fixed 2× frame generation, Balanced (1 frame), and 50% motion-estimation resolution. See [Eden preset](docs/eden-preset.md).

## Recommended GPU Drivers — Adreno 740

| Driver | Status |
| --- | --- |
| [TurnipZ 0.3.0](https://github.com/AlexSanz0902/turnip-sd865-z/releases/tag/v0.3.0) | Previous tested configuration; used for the published benchmark readings and saved preset path. |
| [Turnip v27.0.0-R1](https://github.com/StevenMXZ/Adreno-Tools-Drivers/releases/tag/v27.0.0-R1) by StevenMXZ | Newly tested; I experienced smoother gameplay, but did not record a new controlled benchmark or the exact ZIP selected. |
| Other drivers | Performance and compatibility are not established by this project. |

The AYN Thor Max uses Snapdragon 8 Gen 2 with Adreno 740. StevenMXZ’s release identifies the `Turnip_Gen8_V38` packages as A8xx builds, so they are not the default for Adreno 740. The regular `Turnip_v27.0.0-R1.zip` is the expected 6xx/7xx starting point; the OneUI archive is specialized for relevant Samsung environments. Because my exact ZIP was not recorded, this is compatibility guidance rather than a claim about the precise tested file.

Install a compatible ZIP through Eden’s **GPU Driver Manager**, select it for TOTK, restart Eden, and check stability, rendering, FPS, and frame pacing. Keep the previous driver available so you can switch back. Do not install systemwide components unless the developer explicitly instructs you to. Read [GPU drivers](docs/gpu-drivers.md).

## Performance benchmarks

These readings belong to the **earlier TurnipZ 0.3.0 configuration**, not Turnip v27.0.0-R1:

| Location | UltraCam 2.7.1 | UltraCam 3.0.0 | Relative difference |
| --- | ---: | ---: | ---: |
| Overworld | 35 FPS | 40 FPS | +14.29% |
| Shrines | 45 FPS | 55 FPS | +22.22% |

They are my observed readings, not independently reproduced benchmarks or guaranteed sustained rates. Fixed 2× frame generation was enabled, and the supplied material does not establish whether the counter includes generated frames. My later “smoother” Turnip v27.0.0-R1 report is qualitative and does not prove higher average FPS, 1% lows, or a specific mechanism. See [Benchmarks](docs/benchmarks.md).

## Frame generation

The preset enables fixed 2× frame generation, a Balanced one-frame queue, and 50% motion-estimation resolution. Interpolated output frames are separate from native game-rendered FPS and can affect latency, visual quality, and displayed counter behavior. Read [Frame generation](docs/frame-generation.md).

## Troubleshooting

- **2.7.1 remains near 30 FPS on 1.4.1/1.4.2:** this matches my tests even when FOV and render-distance changes work. Use 3.0.0 for these updates.
- **3.0.0 ignores the INI:** verify `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini` and remove duplicate `sdmc` or `UltraCam` folders.
- **Preset selects the wrong driver:** select the installed driver manually after import; do not guess an Android path.
- **Crashes or artifacts:** disable conflicts, restore the previous driver, and test conservative settings.

See [Troubleshooting](docs/troubleshooting.md).

## Credits and licensing

- **MaxLastBreath:** original NX Optimizer and UltraCam development.
- **MPDERPER:** Android adaptation, configuration, troubleshooting, testing, and packaging.
- **StevenMXZ:** Adreno-Tools-Drivers and the linked Turnip v27.0.0-R1 release.
- **ChatGPT:** technical assistance with validation and documentation.

The unchanged UltraCam binaries are redistributed under MaxLastBreath’s published **CC BY-NC 2.0** notice. No ROM, update, firmware, keys, emulator binary, or GPU-driver binary is included. See [LICENSING.md](LICENSING.md), [CREDITS.md](CREDITS.md), and [PROVENANCE.md](PROVENANCE.md).

## Disclaimer

This project is not affiliated with or endorsed by MaxLastBreath, Nintendo, Eden, StevenMXZ, or the TurnipZ developers. Use legally obtained game content. Back up your data. Results vary by hardware, driver, emulator build, game update, scene, mods, and thermal conditions.
