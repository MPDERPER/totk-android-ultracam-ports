# Reported benchmarks

| Location | UltraCam 2.7.1 | UltraCam 3.0.0 | Difference |
| --- | ---: | ---: | ---: |
| Overworld | 35 FPS | 40 FPS | `(40-35)/35 = 14.29%` |
| Shrines | 45 FPS | 55 FPS | `(55-45)/45 = 22.22%` |

These values come from my tests on an AYN Thor Max with Snapdragon 8 Gen 2, Adreno 740, Eden Nightly, TurnipZ 0.3.0, handheld mode, and fixed 2× frame generation. They are observed readings, not guaranteed minimums or sustained-rate measurements, and they were not independently reproduced by Codex.

Overworld scenes commonly include more terrain, vegetation, distant objects, and variable rendering load. Shrines are often enclosed, but no two areas are identical. The table must not be generalized to every location.

The comparison does not isolate the UltraCam executable as the only changed variable. Configuration differences, caches, scene choice, temperature, driver state, and measurement method may contribute. No recordings or frame-time captures were supplied.
