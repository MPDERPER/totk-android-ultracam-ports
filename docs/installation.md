# Installation

This guide keeps the ExeFS add-on, UltraCam configuration, and Eden per-game preset separate. Mixing their destinations is the most common installation error.

## 1. Requirements

- A compatible Android device and Eden Nightly.
- A legally obtained copy of TOTK.
- One UltraCam ExeFS ZIP from this project's release.
- The UltraCam 3.0.0 configuration ZIP when using 3.0.0.
- Optionally, the Eden per-game preset and TurnipZ 0.3.0.
- A file manager able to work with Eden's selected data directory or virtual SD card.

The preset was tested in Eden Nightly. Other emulators may use different paths, controls, and configuration formats.

## 2. Choose one UltraCam version

Download either `totk-ultracam-2.7.1-eden-720p.zip` or `totk-ultracam-3.0.0-eden-720p.zip`. Never enable both at the same time. Disable other mods that replace `main.npdm`, `subsdk3`, Dynamic FPS, resolution, or UltraCam settings.

## 3. Install the ExeFS add-on

1. Close TOTK.
2. Open Eden and select or long-press TOTK to open its game properties.
3. Open **Add-ons**.
4. Install or select the chosen UltraCam package using the controls available in your Eden Nightly build.
5. Confirm the installed mod has this effective structure:

```text
UltraCam version folder/
└── exefs/
    ├── main.npdm
    └── subsdk3
```

Selecting a parent directory that contains another mod folder can leave `exefs` one level too deep and prevent Eden from recognizing it.

## 4. Install the 3.0.0 configuration

This step is for UltraCam 3.0.0. It is not another add-on.

Extract `totk-ultracam-3.0.0-android-config.zip` into Eden's virtual SD-card root. Preserve the archive structure so the final files are:

```text
sdmc/
└── UltraCam/
    └── TOTK/
        └── Config/
            ├── maxlastbreath.ini
            └── PaletteCFG.json
```

The required INI location is `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini`. If your file manager is already showing the virtual `sdmc` root, copy the `UltraCam` folder there. Do not create `sdmc/sdmc/UltraCam/...`.

## 5. UltraCam 2.7.1 configuration limitation

The original 2.7.1 layout reads a legacy configuration from `romfs/UltraCam/maxlastbreath.ini`. The supplied 2.7.1 package contains only ExeFS files, and no compatible 2.7.1 RomFS configuration was provided for this release. The 3.0.0 SD-card configuration is not advertised as interchangeable. Users who need custom 2.7.1 values must obtain or create a compatible legacy RomFS configuration through the upstream workflow.

## 6. Install TurnipZ 0.3.0 (optional)

TurnipZ 0.3.0 was used in my test setup but is not a universal requirement and is not bundled here.

1. Download it from the developer's [v0.3.0 release](https://github.com/AlexSanz0902/turnip-sd865-z/releases/tag/v0.3.0).
2. Open Eden's **GPU Driver Manager**.
3. Install the driver ZIP and select it for TOTK as appropriate.
4. If it causes crashes or graphical corruption, restore Eden's system/default driver or another driver known to work on your Adreno generation.

Different Adreno generations can respond differently to custom drivers.

## 7. Import the Eden per-game preset (optional)

The preset can overwrite existing TOTK preferences. Export or back up your current per-game configuration first.

1. Download `0100F2C0115B6000.ini`.
2. In Eden, open TOTK's game properties.
3. Locate the **Settings** row. Eden's current Android game-properties screen exposes **Import Config** as a secondary action once a per-game configuration exists. If needed, first open Settings and change one game-specific option so Eden creates the file.
4. Choose **Import Config** and select the downloaded INI.
5. Reopen the game's settings and verify CPU, graphics, handheld mode, and frame-generation values.
6. Open the GPU Driver Manager and confirm TurnipZ 0.3.0 is installed and selected. The preset contains my device-specific path and cannot install the driver itself.
7. Fully restart Eden.

Eden copies the selected file to its internal user directory as `config/custom/0100F2C0115B6000.ini`. Direct Android file access is unnecessary when the import action is present. If your build does not expose **Import Config**, update to a build that supports it or use Eden's own user-data access/export facilities; do not guess an inaccessible Android app-data path.

To revert, restore your exported configuration, reset TOTK's per-game settings through Eden, or remove the custom settings and return individual options to global/default values.

## 8. Verify frame generation

After import, confirm:

```text
Frame Generation: On
Target frame rate: Use a fixed multiplier
Frame multiplier: 2×
Frame queue target: Balanced (1 frame)
Motion estimation resolution: 50%
```

## 9. Launch and test

Restart Eden and launch TOTK. With UltraCam 3.0.0, hold **ZL + ZR** and press **L3** to open the controller-accessible menu. Upstream also documents F12 with a keyboard. Check that the configuration loads, game speed remains normal, graphics are correct, and frame pacing is acceptable. If the INI is ignored, recheck the exact SD-card path and folder nesting.
