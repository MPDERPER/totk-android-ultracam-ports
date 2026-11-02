# Reported performance

| Location | UltraCam 2.7.1 | UltraCam 3.0.0 | Relative difference |
| --- | ---: | ---: | ---: |
| Overworld | 35 FPS | 40 FPS | +14.29% |
| Shrines | 45 FPS | 55 FPS | +22.22% |

These readings belong to my **earlier TurnipZ 0.3.0 configuration** on an AYN Thor Max with Snapdragon 8 Gen 2, Adreno 740, Eden Nightly, handheld 720p, 21,000 custom CPU ticks, and fixed 2× frame generation. They are observed readings, not guaranteed minimums, controlled sustained-rate measurements, or independently reproduced results.

The comparison does not isolate the UltraCam executable as the only variable. Configuration, caches, scene choice, temperature, driver state, and measurement method may contribute. The FPS counter’s treatment of generated frames is unknown, so the values are not confirmed native game-rendered FPS.

## Later driver observation

I later tested a driver from StevenMXZ’s [Turnip v27.0.0-R1 release](https://github.com/StevenMXZ/Adreno-Tools-Drivers/releases/tag/v27.0.0-R1) and experienced smoother gameplay. I did not preserve the exact selected ZIP or collect a new controlled benchmark, average-FPS series, 1% lows, or frame-time capture. The table above must therefore remain attributed to TurnipZ 0.3.0.

“Smoother” can describe frame pacing, visible stutter, rendering behavior, shader/cache behavior, or workload compatibility without proving higher average FPS. This project does not claim which mechanism caused my observation or a percentage improvement. See [GPU drivers](gpu-drivers.md) and [Frame generation](frame-generation.md).
