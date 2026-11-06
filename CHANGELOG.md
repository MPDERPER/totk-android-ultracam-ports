# Changelog

## Stable preset correction — 2026-11-06

- Replaced the v1.1.0 Stable preset with the newly supplied `EDEN STABLE SETTINGS.ini` as the base.
- Enabled Docked Mode by setting `use_docked_mode = 1` with matching non-default metadata.
- Preserved the corrected preset's `scaling_filter = 0` value and every other supplied setting.
- Updated the published asset, checksum file, release notes, README, and provenance. No UltraCam executable or 900p configuration value changed.

## v1.1.0-900p-docked — 2026-11-06

- Added a quality-focused UltraCam 3.0.0 preset targeting 1600 × 900 in Eden Stable Docked Mode.
- Preserved the supplied `ShadowResolution = 512`, 5000 render distance, FOV 45, FSR, Dynamic FPS, 60 FPS target, shader toggles, time-speed values, LOD settings, and disabled handheld-resolution override.
- Added separate ExeFS, virtual-SD configuration, and Eden Stable preset downloads with distinct installation paths.
- Documented my AYN Thor Max observation of approximately 5 FPS less overworld performance than the 720p preset while shrines still reached approximately 60 FPS.
- Reworked the main README around 720p versus 900p choices, Docked Mode, beginner installation, preset import, GPU-driver selection, verification, and troubleshooting.
- Corrected the v1.0.0 README links to the actual published filenames: `ULTRACAM.zip`, `regular.Eden.totk.ini`, and `Nightly.Eden.Totk.ini`.
- Preserved the existing 720p release and its historical observations.

## Standard Eden performance findings — 2026-11-03

- Documented my latest UltraCam 3.0.0 results on Standard Eden at 1280 × 720 on an AYN Thor Max: approximately 50 FPS in the overworld and 60 FPS in shrines without frame generation.
- Compared those readings with the previous Eden Nightly observations of approximately 40 FPS in the overworld and 55 FPS in shrines.
- Recorded the arithmetic differences as +25% and approximately +9.1% comparisons of reported readings only, not proven native-FPS improvements or evidence of a confirmed Nightly regression.
- Preserved the earlier Nightly and UltraCam 2.7.1 results as historical observations and added requirements for a future controlled comparison.
- Changed documentation only. No UltraCam binary, ZIP package, INI configuration, GPU setting, benchmark preset, or release asset was modified.

## Documentation correction — 2026-11-02

- Corrected UltraCam 2.7.1 compatibility: its graphics modifications remain partially functional on TOTK 1.4.1 and 1.4.2, but its FPS unlock did not work in my tests and gameplay stayed around 30 FPS.
- Documented my base-game 1.0.0 observation separately from MaxLastBreath’s historical upstream support listings.
- Made UltraCam 3.0.0 the clear recommendation for my tested 1.4.1 and 1.4.2 configurations.
- Expanded the README Quick Installation Guide and the detailed ExeFS, legacy RomFS, virtual-SD, and Eden preset instructions.
- Added Adreno 740 guidance for StevenMXZ’s Turnip v27.0.0-R1 release and distinguished regular, OneUI, and A8xx Gen8 V38 archives.
- Recorded my later smoother-gameplay observation without inventing an FPS increase or new benchmark.
- Preserved the TurnipZ 0.3.0 attribution for the original benchmark readings and the unchanged released Eden preset.
- Updated troubleshooting and release notes. No executable, configuration asset, benchmark preset, or release download was changed.

## v1.0.0-android-ports — 2026-11-01

- Initial Android community release of unchanged UltraCam 2.7.1 and 3.0.0 ExeFS payloads.
- Added the tested UltraCam 3.0.0 SD-card configuration.
- Added the optional Eden Nightly per-game preset.
- Documented installation, configuration paths, frame generation, benchmarks, compatibility, troubleshooting, attribution, licensing, and provenance.
