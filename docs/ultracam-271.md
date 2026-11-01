# UltraCam 2.7.1 Android package

The 2.7.1 asset contains unchanged upstream `main.npdm` and `subsdk3` files inside an Eden-compatible ExeFS mod folder. The files match tag `manager-3.1.0` in MaxLastBreath's repository.

This release does not include a 2.7.1 RomFS configuration. Historical upstream layout places that file at `romfs/UltraCam/maxlastbreath.ini`. Do not install the 3.0.0 SD-card configuration and assume 2.7.1 will read it.

My reported readings were 35 FPS in an overworld test and 45 FPS in a shrine test. See [benchmarks.md](benchmarks.md) for limitations.
