# TOTK Android UltraCam Ports

Community-maintained Android packages for **MaxLastBreath's UltraCam 2.7.1 and UltraCam Calamity 3.0.0**, prepared for *The Legend of Zelda: Tears of the Kingdom* in Eden Nightly.

[Download the latest release](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/latest) · [Installation guide](docs/installation.md) · [Troubleshooting](docs/troubleshooting.md)

I manually adapted, configured, packaged, and tested these Android setups. **I did not create UltraCam.** The original UltraCam and NX Optimizer software was developed by [MaxLastBreath](https://github.com/MaxLastBreath/nx-optimizer). This is an unofficial community project.

## What is included

The release contains four separate downloads:

| Asset | Purpose |
| --- | --- |
| `totk-ultracam-2.7.1-eden-720p.zip` | UltraCam 2.7.1 ExeFS add-on. |
| `totk-ultracam-3.0.0-eden-720p.zip` | UltraCam 3.0.0 ExeFS add-on. |
| `totk-ultracam-3.0.0-android-config.zip` | UltraCam 3.0.0 SD-card configuration, including `maxlastbreath.ini` and `PaletteCFG.json`. |
| `0100F2C0115B6000.ini` | Optional Eden Nightly per-game preset for TOTK. |

Install **only one** UltraCam ExeFS version at a time. The executable add-on, UltraCam configuration, and Eden per-game preset use three different installation procedures.

## Version comparison

| | UltraCam 2.7.1 | UltraCam 3.0.0 |
| --- | --- | --- |
| ExeFS installation | Eden game add-ons | Eden game add-ons |
| Configuration location | Legacy `romfs/UltraCam/maxlastbreath.ini` | Virtual SD card: `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini` |
| Configuration in this release | **Not included**; no compatible 2.7.1 RomFS configuration was supplied | Included as a separate ZIP |
| In-game menu shortcut | Build-specific; not verified for this package | Hold **ZL + ZR**, then press **L3**; also documented upstream as F12 with a keyboard |
| Reported overworld result | 35 FPS | 40 FPS |
| Reported shrine result | 45 FPS | 55 FPS |

The 2.7.1 download is therefore an executable-only port. Do not assume the 3.0.0 SD-card configuration is compatible with 2.7.1.

## My reported performance

| Test location | UltraCam 2.7.1 | UltraCam 3.0.0 | Relative difference |
| --- | ---: | ---: | ---: |
| Overworld | 35 FPS | 40 FPS | +14.29% |
| Shrines | 45 FPS | 55 FPS | +22.22% |

These are observed readings from my testing. They are not guaranteed minimums or independently reproduced benchmarks. My Eden preset enables **fixed 2× frame generation**, and the supplied material does not establish whether the displayed readings include generated frames. Do not interpret them as confirmed native, game-rendered FPS. Other configuration differences may also contribute to the observed gap.

### Tested setup — AYN Thor Max / Eden Nightly

| Component | Tested configuration |
| --- | --- |
| Device | AYN Thor Max |
| SoC / GPU | Snapdragon 8 Gen 2 / Adreno 740 |
| Emulator | Eden Nightly |
| GPU driver | [TurnipZ 0.3.0](https://github.com/AlexSanz0902/turnip-sd865-z/releases/tag/v0.3.0) |
| Game rendering target | 1280 × 720, handheld mode |
| Frame generation | Enabled; fixed multiplier; 2× |
| Frame queue target | Balanced (1 frame) |
| Motion-estimation resolution | 50% |
| Custom CPU ticks | Enabled; 21000 |

I referred to part of my setup as “CPU Debug in FreeDeno settings.” Eden exposes separate **Custom CPU Ticks** and **Freedreno Settings** controls. The exported preset proves the custom tick values above, but it does not contain a key literally named `cpu_debug`; I therefore keep that phrase as a user-reported description rather than equating the two features.

## Frame generation

The preset contains:

```ini
frame_gen=true
frame_gen_multiplier=2
frame_gen_target_rate=0
frame_gen_flow_scale_auto=false
frame_gen_flow_scale=50
frame_gen_queue_target=1
```

Eden's current Android interface maps these values to **On**, **2×**, **Use a fixed multiplier**, **50% motion estimation**, and **Balanced (1 frame)**. Frame generation inserts interpolated output frames between rendered frames. It may improve perceived smoothness, but it does not increase the game's simulation rate and can add latency or visual artifacts. See [Frame generation](docs/frame-generation.md).

## Community-tested game versions

I report that both packages worked in my Android setup through **TOTK 1.4.2**. I repeatedly encountered crashes on **1.4.3**. MaxLastBreath's current upstream documentation lists 1.4.0 and 1.4.1 as partial and lists 1.4.2 as supported for the current release; the older 2.7.1 build has a narrower historical support context. My Android results are not official upstream support or a universal compatibility guarantee. See [Compatibility](docs/compatibility.md).

## Quick installation

1. Back up your Eden per-game settings and existing mods.
2. Download **one** ExeFS ZIP from the release.
3. In Eden, open TOTK's game properties and install or select that package under **Add-ons**. The selected mod folder must contain `exefs/main.npdm` and `exefs/subsdk3` directly below it.
4. For UltraCam 3.0.0, separately extract the configuration ZIP into Eden's virtual SD card so the final file is `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini`.
5. Optionally install TurnipZ 0.3.0 through Eden's GPU Driver Manager, then import `0100F2C0115B6000.ini` from the TOTK game-properties screen. Recheck the active driver after import because the preset contains my device-specific Android path.
6. Fully restart Eden, launch the game, and verify game speed, graphics, frame pacing, and temperatures.

Read the [complete installation guide](docs/installation.md) before installing. The imported preset can replace your existing per-game preferences.

## Configuration highlights

The supplied UltraCam 3.0.0 configuration targets 1280 × 720 and enables Dynamic FPS. It uses 60 FPS gameplay/menu limits, a 30 FPS movie limit, shadow resolution 206, render distance 5000, FOV 45, FSR on, FXAA off, and disables ambient occlusion, bloom, screen-space reflections, and volumetric fog. `IsTimeSlower=False` and `TimeSpeed=1.00` preserve normal time speed. See [Configuration reference](docs/configuration.md).

## Gameplay recordings & performance showcase

No recordings or screenshots were supplied with this release. The performance table records my reported observations only; it is not backed by uploaded footage or independent capture data.

## Credits and license

- **MaxLastBreath:** original NX Optimizer and UltraCam development.
- **MPDERPER:** manual Android adaptation, configuration, optimization, troubleshooting, testing, and packaging.
- **ChatGPT:** technical assistance with validation and documentation.

The unchanged upstream binaries are redistributed under MaxLastBreath's published **CC BY-NC 2.0** notice. This means attribution and noncommercial terms apply. No ROM, game update, firmware, cryptographic keys, emulator binary, GPU-driver binary, or Nintendo game assets are included. See [LICENSING.md](LICENSING.md) and [PROVENANCE.md](PROVENANCE.md).

## Disclaimer

This project is not affiliated with or endorsed by MaxLastBreath, Nintendo, Eden, or the TurnipZ developers. Use legally obtained game content. Back up your data. Results vary by hardware, driver, emulator build, game update, scene, other mods, and thermal conditions.

