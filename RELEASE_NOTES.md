# TOTK Android UltraCam Ports v1.0.0

I am publishing my Android packages for MaxLastBreath’s UltraCam 2.7.1 and UltraCam Calamity 3.0.0, together with my tested 720p configuration and optional Eden Nightly per-game preset.

## Installation — read this first

Follow the complete **[Installation Guide — Eden Nightly (Android)](https://github.com/MPDERPER/totk-android-ultracam-ports#installation-guide-eden-nightly-android)** in the main README. It includes direct downloads, separate UltraCam 2.7.1 and 3.0.0 instructions, the Eden preset import, GPU-driver setup, frame-generation values, verification, common mistakes, and troubleshooting.

The UltraCam **ExeFS add-on** is installed through TOTK’s **Add-ons** interface. The separate UltraCam 3.0.0 configuration is extracted into Eden’s virtual **`sdmc`** root so the INI ends at `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini`; it is not installed through Add-ons. Enable only one UltraCam ExeFS version at a time.

**Compatibility warning:** UltraCam 2.7.1 still applied graphics changes on TOTK 1.4.1 and 1.4.2 in my tests, but its FPS unlock did not work and gameplay remained around 30 FPS. I recommend UltraCam 3.0.0 for those updates.

## Compatibility correction

- **UltraCam 2.7.1:** the 60 FPS unlock worked on the unupdated 1.0.0 base game in my testing. On TOTK 1.4.1 and 1.4.2, the package still loads and applies graphics changes such as render distance and FOV, but the FPS unlock does not work and gameplay remains around 30 FPS.
- **UltraCam 3.0.0:** recommended for TOTK 1.4.1 and 1.4.2. Its FPS unlock and working graphics optimizations remain functional in my tested configurations.
- **TOTK 1.4.3:** I encountered repeated crashes in my Android setup. This is not a universal incompatibility claim.

Historical upstream metadata lists 1.1.0–1.2.1 for 2.7.1 and adds 1.4.0–1.4.2 for 3.0.0. My Android observations are separate from those upstream listings.

Read the [complete installation guide in the README](https://github.com/MPDERPER/totk-android-ultracam-ports#installation-guide-eden-nightly-android) and the [compatibility table](https://github.com/MPDERPER/totk-android-ultracam-ports/blob/main/docs/compatibility.md).

## Downloads

- `totk-ultracam-2.7.1-eden-720p.zip`: unchanged 2.7.1 ExeFS payload. The legacy RomFS INI is not included; the ExeFS-only package can still perform its built-in behavior.
- `totk-ultracam-3.0.0-eden-720p.zip`: unchanged 3.0.0 ExeFS payload.
- `totk-ultracam-3.0.0-android-config.zip`: extract into Eden’s virtual SD-card root so the final INI is `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini`.
- `0100F2C0115B6000.ini`: optional TOTK per-game preset. Back up first, import through Eden, and reselect your installed GPU driver.

Install only one UltraCam ExeFS version at a time.

## GPU drivers

TurnipZ 0.3.0 was used for the original benchmark setup and remains referenced by the released preset. I later tested a driver from StevenMXZ’s [Turnip v27.0.0-R1 release](https://github.com/StevenMXZ/Adreno-Tools-Drivers/releases/tag/v27.0.0-R1) and experienced smoother gameplay. I did not record the exact ZIP or new controlled measurements, so this is a qualitative observation and the original benchmark attribution is unchanged. No GPU-driver binary is included.

## Original reported performance — TurnipZ 0.3.0

| Location | UltraCam 2.7.1 | UltraCam 3.0.0 |
| --- | ---: | ---: |
| Overworld | 35 FPS | 40 FPS |
| Shrines | 45 FPS | 55 FPS |

These are my observed readings, not independently reproduced benchmarks or guaranteed rates. Fixed 2× frame generation was enabled, and the FPS counter’s treatment of generated frames is unknown.

## Credits and license

UltraCam and NX Optimizer were developed by [MaxLastBreath](https://github.com/MaxLastBreath/nx-optimizer). I performed the Android adaptation, configuration, testing, and packaging with technical assistance from ChatGPT. StevenMXZ developed the linked Adreno-Tools-Drivers release. The unchanged UltraCam binaries are redistributed under CC BY-NC 2.0. No game files, ROMs, updates, keys, firmware, emulator binary, GPU-driver binary, or Nintendo assets are included.
