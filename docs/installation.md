# Installation

This guide keeps four different components separate: the UltraCam ExeFS add-on, the legacy 2.7.1 RomFS customization path, the 3.0.0 virtual-SD configuration, and Eden’s optional per-game preset. The complete beginner workflow also appears directly in the [main README](../README.md#installation-guide--read-this-first).

## 900p Docked quick reference

The [v1.1.0 900p Docked release](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/tag/v1.1.0-900p-docked) uses three separate downloads:

1. Install [`UltraCam 3.0.0.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.1.0-900p-docked/UltraCam.3.0.0.zip) through TOTK's **Add-ons** manager. [`UltraCam 2.7.1.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.1.0-900p-docked/UltraCam.2.7.1.zip) is also available for legacy use, but only one executable version may be enabled.
2. Extract the `UltraCam` folder from [`UltraCam 900p.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.1.0-900p-docked/UltraCam.900p.zip) directly into Eden Stable's existing virtual `sdmc` root.
3. Import [`EDEN STABLE SETTINGS.ini`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.1.0-900p-docked/EDEN.STABLE.SETTINGS.ini) through Eden Stable's per-game **Import Config** action.
4. Enable **Docked Mode**, restart Eden, and verify 1600 × 900 with `ShadowResolution = 512`.

> **IMPORTANT: THIS IS THE 900P DOCKED PRESET. ENABLE DOCKED MODE IN EDEN BEFORE PLAYING.**

The final configuration path is `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini`. Do not install the SDMC configuration through Add-ons, and do not copy the ExeFS files into `sdmc`. Back up an existing 720p configuration before replacing it. The following sections also document the older 720p and 2.7.1 workflows.

## Before installing

1. Back up TOTK’s current per-game settings and existing mods.
2. Record your game update, Eden build, device, and working GPU driver.
3. Disable other UltraCam, Dynamic FPS, FPS, resolution, `main.npdm`, or `subsdk3` modifications.
4. Download **one** UltraCam ExeFS ZIP. Never enable 2.7.1 and 3.0.0 together.
5. Prefer UltraCam 3.0.0 for TOTK 1.4.1 or 1.4.2. My 2.7.1 FPS unlock did not work on those updates.

## Install UltraCam 2.7.1

1. Download `totk-ultracam-2.7.1-eden-720p.zip` from the [release](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/tag/v1.0.0-android-ports).
2. Extract it if your Eden build requires an unpacked add-on directory.
3. Open Eden, select TOTK, and open the game’s **Add-ons** section.
4. Import or select the UltraCam 2.7.1 package and make sure it is enabled.
5. Confirm the effective structure is:

```text
UltraCam 2.7.1/
└── exefs/
    ├── main.npdm
    └── subsdk3
```

6. Disable conflicting mods, fully restart Eden, and launch the game.

The original 2.7.1 customization system expects:

```text
romfs/UltraCam/maxlastbreath.ini
```

This release does not include that legacy INI. It is not mandatory for every executable behavior: I observed the ExeFS-only package running the 1.0.0 base game with the FPS unlock working. The legacy file is the original customization path. Do not assume the 3.0.0 SD-card INI is compatible with 2.7.1, and do not expect a RomFS INI alone to make the old FPS patch work on 1.4.x.

On TOTK 1.4.1 and 1.4.2, my 2.7.1 package still loaded and applied FOV, render-distance, and other graphics changes, but gameplay remained around 30 FPS. Use 3.0.0 when FPS unlocking is required on those updates.

## Install UltraCam 3.0.0

### Part 1 — ExeFS add-on

1. Download `totk-ultracam-3.0.0-eden-720p.zip`.
2. Open TOTK’s **Add-ons** section in Eden.
3. Import or select the package and make sure it is enabled.
4. Confirm the structure is:

```text
UltraCam 3.0.0/
└── exefs/
    ├── main.npdm
    └── subsdk3
```

### Part 2 — virtual-SD configuration

1. For the existing 720p release, download [`ULTRACAM.zip`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/ULTRACAM.zip). For 900p, use the v1.1.0 configuration linked above.
2. Locate Eden’s virtual SD-card root.
3. Extract the ZIP into that root while preserving the archive’s folders.
4. Confirm the final layout is:

```text
Eden/
└── sdmc/
    └── UltraCam/
        └── TOTK/
            └── Config/
                ├── maxlastbreath.ini
                └── PaletteCFG.json
```

The required INI path is `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini`. This configuration ZIP does **not** belong in the Add-ons manager.

### Common mistakes

- Installing the configuration INI through Add-ons.
- Leaving the ZIP in the destination instead of extracting it.
- Creating `sdmc/sdmc/UltraCam`.
- Creating `UltraCam/UltraCam/TOTK`.
- Running 2.7.1 and 3.0.0 together.
- Leaving another FPS or `subsdk3` mod enabled.
- Editing a duplicate INI that UltraCam is not reading.

### Verify UltraCam 3.0.0

1. Fully restart Eden.
2. Launch TOTK and confirm normal game speed, graphics, resolution, and frame pacing.
3. Hold **ZL + ZR** and click the left stick (**L3**) to open the menu in my tested controller configuration.
4. Verify the FPS and resolution values.
5. If nothing changes, recheck the exact virtual-SD path and disable conflicts.

## Import an Eden per-game preset

The emulator preset is not UltraCam’s `maxlastbreath.ini`. Use `EDEN STABLE SETTINGS.ini` for the new 900p Stable workflow, [`regular.Eden.totk.ini`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/regular.Eden.totk.ini) for the previous Standard Eden export, or [`Nightly.Eden.Totk.ini`](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/download/v1.0.0-android-ports/Nightly.Eden.Totk.ini) for the previous Nightly export.

1. Back up your current TOTK per-game settings.
2. Download the preset intended for your Eden build and release.
3. Open TOTK’s properties in Eden and use **Import Config**.
4. Import the file and review the resulting CPU, graphics, and frame-generation settings.
5. Open the GPU Driver Manager and manually select a driver appropriate for your GPU.
6. Confirm Docked Mode for the 900p preset, then fully restart Eden.

Each exported preset can contain an Android-specific driver path. Importing it does not install that driver, and the path may not exist elsewhere. Do not replace it with a guessed path. Select the desired installed driver through Eden after importing. The v1.1.0 Stable preset references a Balemuni Apex package used on the tested Snapdragon 8 Gen 2 device; the older published preset was associated with TurnipZ 0.3.0.

The v1.1.0 Stable asset is the newly supplied `EDEN STABLE SETTINGS.ini` preserved byte-for-byte. It retains `scaling_filter = 0` and leaves `use_docked_mode = 0`, so 900p users must manually enable Docked Mode after importing it.

## Install a custom GPU driver — Adreno 740

1. Open StevenMXZ’s official [Turnip v27.0.0-R1 release](https://github.com/StevenMXZ/Adreno-Tools-Drivers/releases/tag/v27.0.0-R1).
2. Confirm the package matches your GPU. For Adreno 740, the regular `Turnip_v27.0.0-R1.zip` is the expected 6xx/7xx starting point. The Gen8 V38 archives are A8xx builds; the OneUI archive is specialized for relevant Samsung environments.
3. Download the AdrenoTools-compatible ZIP without extracting or installing system components unless the developer instructs you to.
4. Open Eden’s **GPU Driver Manager**, import/install the ZIP, and select it for TOTK.
5. Restart Eden if required, then test stability, rendering, FPS, and frame pacing.
6. If behavior worsens, reselect the previous working driver or system/default driver and restart.

I later experienced smoother gameplay with a driver from that release, but did not preserve the exact selected ZIP or collect new controlled measurements. TurnipZ 0.3.0 remains the driver associated with the published benchmark table and original preset. See [GPU drivers](gpu-drivers.md).

## Final verification checklist

- Exactly one UltraCam ExeFS package is enabled.
- `exefs` is directly under the selected add-on folder.
- The 3.0.0 INI is at `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini`.
- The Eden preset was imported through Eden and is not treated as an UltraCam INI.
- The selected GPU driver is installed and appropriate for the device.
- TOTK runs at normal speed and expected graphics settings.
- On 1.4.1/1.4.2, UltraCam 3.0.0 is selected if FPS unlocking is required.

If verification fails, use [Troubleshooting](troubleshooting.md).
