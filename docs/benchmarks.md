# Reported performance

## New observation — Standard Eden with UltraCam 3.0.0

My latest real-world test used the following setup:

| Component | Test condition |
| --- | --- |
| Device | AYN Thor Max |
| Chipset / GPU | Snapdragon 8 Gen 2 / Adreno 740 |
| Emulator | Standard Eden stable/main release, not Eden Nightly |
| UltraCam | 3.0.0 |
| Resolution | 1280 × 720 |
| Frame generation | Disabled / unavailable in the tested build |
| Other settings | Kept consistent with the previous configuration, including FreeDeno settings, CPU configuration, UltraCam INI, and GPU-driver choice |

### Observed gameplay readings

- **Overworld: approximately 50 FPS**
- **Shrines: approximately 60 FPS**

These are my actual displayed gameplay readings without frame generation. They were not independently reproduced and are not guaranteed sustained rates, controlled averages, 1% lows, or frame-time measurements.

The supplied Standard Eden per-game INI retains inherited `frame_gen` configuration fields from the prior setup. The tested Standard Eden build did not make frame generation available or active, so the presence of those stored keys does not mean generated frames contributed to the reported 50/60 FPS readings.

## Standard Eden versus the previous Eden Nightly observation

| Emulator build | UltraCam | Resolution | Frame generation | Overworld | Shrines | Difference from Nightly |
| --- | --- | --- | --- | ---: | ---: | --- |
| **Standard Eden (stable/main)** | 3.0.0 | 1280 × 720 | **Disabled / unavailable** | **~50 FPS** | **~60 FPS** | Overworld **+25% reported**; shrines **+9.1% reported** |
| Eden Nightly — previous observation | 3.0.0 | 1280 × 720 | Fixed 2× configured | ~40 FPS | ~55 FPS | Baseline for this informal comparison |

The arithmetic differences are `(50 - 40) / 40 = 25%` for the overworld and `(60 - 55) / 55 ≈ 9.1%` for shrines. They compare reported counter readings only. They do **not** prove native-FPS improvements of 25% or 9.1%, because the test was informal and it remains unknown whether the earlier Nightly FPS counter included generated frames.

Standard Eden delivered higher observed FPS in this test despite being a less frequently updated release. It may therefore be a preferable option for some UltraCam 3.0.0 users on similar hardware, but further testing is required. This result does not prove that Eden Nightly has regressed and does not isolate UltraCam as the cause. Emulator implementation differences, CPU/GPU scheduling, Vulkan behavior, frame pacing, caches, temperature, scene selection, and measurement methodology are plausible explanations, not confirmed causes.

A controlled follow-up should use the same overworld and shrine locations, save file, driver, 1280 × 720 resolution, FPS counter, temperature conditions, and frame-generation state. The exact Standard Eden build number, test duration, 1% lows, and frame-time data were not recorded and are not inferred here.

## Historical Eden Nightly observations

| Location | UltraCam 2.7.1 | UltraCam 3.0.0 | Relative difference |
| --- | ---: | ---: | ---: |
| Overworld | 35 FPS | 40 FPS | +14.29% |
| Shrines | 45 FPS | 55 FPS | +22.22% |

These readings belong to my **earlier TurnipZ 0.3.0 configuration** on an AYN Thor Max with Snapdragon 8 Gen 2, Adreno 740, Eden Nightly, handheld 720p, 21,000 custom CPU ticks, and fixed 2× frame generation. They remain preserved as historical observed readings, not guaranteed minimums, controlled sustained-rate measurements, or independently reproduced results.

The historical comparison does not isolate the UltraCam executable as the only variable. Configuration, caches, scene choice, temperature, driver state, and measurement method may contribute. The previous FPS counter’s treatment of generated frames is unknown, so those values are not confirmed native game-rendered FPS.

## Later driver observation

I later tested a driver from StevenMXZ’s [Turnip v27.0.0-R1 release](https://github.com/StevenMXZ/Adreno-Tools-Drivers/releases/tag/v27.0.0-R1) and experienced smoother gameplay. I did not preserve the exact selected ZIP or collect a new controlled benchmark, average-FPS series, 1% lows, or frame-time capture. The table above must therefore remain attributed to TurnipZ 0.3.0.

“Smoother” can describe frame pacing, visible stutter, rendering behavior, shader/cache behavior, or workload compatibility without proving higher average FPS. This project does not claim which mechanism caused my observation or a percentage improvement. See [GPU drivers](gpu-drivers.md) and [Frame generation](frame-generation.md).
