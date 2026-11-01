# TOTK Android UltraCam Ports v1.0.0

I am publishing my Android packages for MaxLastBreath's UltraCam 2.7.1 and UltraCam Calamity 3.0.0, together with my tested 720p configuration and optional Eden Nightly per-game preset.

## Downloads

- `totk-ultracam-2.7.1-eden-720p.zip`: unchanged 2.7.1 ExeFS payload. No compatible 2.7.1 RomFS configuration was supplied, so this is an executable-only package.
- `totk-ultracam-3.0.0-eden-720p.zip`: unchanged 3.0.0 ExeFS payload.
- `totk-ultracam-3.0.0-android-config.zip`: extract into Eden's virtual SD-card root so the final INI is `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini`.
- `0100F2C0115B6000.ini`: optional TOTK per-game preset. Back up first, use Eden's game-properties **Import Config** action, then reselect TurnipZ 0.3.0 if necessary.

Install only one UltraCam ExeFS version at a time.

## My tested setup

AYN Thor Max, Snapdragon 8 Gen 2, Adreno 740, Eden Nightly, TurnipZ 0.3.0, handheld 720p, 21,000 custom CPU ticks, fixed 2× frame generation, Balanced (1 frame) queue, and 50% motion-estimation resolution.

| Location | UltraCam 2.7.1 | UltraCam 3.0.0 |
| --- | ---: | ---: |
| Overworld | 35 FPS | 40 FPS |
| Shrines | 45 FPS | 55 FPS |

The differences are +14.29% and +22.22% relative to the 2.7.1 readings. These are my observed readings, not independently reproduced benchmarks or guaranteed sustained rates. The FPS counter's treatment of generated frames is unknown, and configuration differences may contribute.

I report successful gameplay through TOTK 1.4.2 and repeated crashes on 1.4.3 in my setup. This is device-specific community testing, not universal compatibility or official support from MaxLastBreath.

## Credits and license

UltraCam and NX Optimizer were developed by [MaxLastBreath](https://github.com/MaxLastBreath/nx-optimizer). I manually adapted, configured, tested, and packaged these Android setups with technical assistance from ChatGPT. The binaries are byte-for-byte matches to their tagged upstream files and are redistributed unchanged under CC BY-NC 2.0. No game files, ROMs, updates, keys, firmware, emulator binary, GPU-driver binary, or Nintendo assets are included.
