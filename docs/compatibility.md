# Compatibility

This page separates **historical upstream version listings** from **my Android observations**. An upstream listing is not a benchmark result, and a package loading in my setup does not make that version officially supported.

## Compatibility summary

| TOTK version | UltraCam 2.7.1 | UltraCam 3.0.0 |
| --- | --- | --- |
| 1.0.0 — base game | 60 FPS unlock worked in my testing. Not in the historical upstream list. | Reported working in my testing. Not in the historical upstream list. |
| 1.1.0–1.2.1 | Officially listed in 2.7.1 metadata. Individual Android versions were not separately benchmarked here. | Officially listed in 3.0.0 metadata. Individual Android versions were not separately benchmarked here. |
| 1.4.0 | Outside the official 2.7.1 list and not separately tested here. | Officially listed in 3.0.0 metadata; not separately benchmarked here. |
| 1.4.1 | **Partial:** loads and applies render-distance/FOV changes, but the FPS unlock does not work and gameplay remains around 30 FPS. | **Recommended:** FPS unlock and working graphics optimizations remain functional in my tests. |
| 1.4.2 | **Partial:** graphics changes work, but the FPS unlock does not and gameplay remains around 30 FPS. | **Recommended:** FPS unlock and working graphics optimizations remain functional in my tests. |
| 1.4.3 | Repeated crashes in my setup. | Repeated crashes in my setup. |

The 1.4.3 entries describe my AYN Thor Max / Eden Nightly experience, not every device, emulator build, driver, or future UltraCam release.

## Historical upstream metadata

MaxLastBreath’s `manager-3.1.0` tag identifies the supplied 2.7.1 payload and lists `1.1.0`, `1.1.1`, `1.1.2`, `1.2.0`, and `1.2.1`.

The `manager-3.2.0` tag identifies the 3.0.0 payload and lists those versions plus `1.4.0`, `1.4.1`, and `1.4.2`.

Sources: [NX Optimizer](https://github.com/MaxLastBreath/nx-optimizer), [2.7.1 metadata](https://github.com/MaxLastBreath/nx-optimizer/blob/manager-3.1.0/src/PatchInfo/Tears%20Of%20The%20Kingdom/PatchInfo.json), and [3.0.0 metadata](https://github.com/MaxLastBreath/nx-optimizer/blob/manager-3.2.0/src/PatchInfo/Tears%20Of%20The%20Kingdom/PatchInfo.json).

## What “partial” means for 2.7.1 on 1.4.1/1.4.2

UltraCam 2.7.1 is not completely broken on these updates. The ExeFS package loads, the game remains playable, and reduced render distance, modified FOV, and other visible graphics settings continue to apply. The FPS unlock no longer works, and gameplay stays at approximately 30 FPS.

This is consistent with a version-specific FPS patch or game-code compatibility issue, but I have not proved the precise binary-level cause. A working graphical modification does not establish a working FPS patch.

## Recommendations

**UltraCam 2.7.1:** use primarily with older TOTK versions. I observed the 60 FPS unlock on the unupdated base game, but 1.0.0 was not officially listed upstream. Expect only partial behavior on 1.4.1 and 1.4.2.

**UltraCam 3.0.0:** use for newer 1.4.1 and 1.4.2 configurations. Its FPS unlocking system and working graphical optimizations remained operational in my tests, and those versions appear in the historical 3.0.0 metadata.

When reporting compatibility, include the game update, Eden build, device/SoC, GPU driver, enabled mods, UltraCam version, and whether the failure affects loading, graphics, FPS unlocking, or all three.
