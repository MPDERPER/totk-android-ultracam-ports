# TOTK Android UltraCam 900p Docked — Quality Preset + Eden Stable Settings

This release adds my quality-focused **1600 × 900** configuration for UltraCam Calamity 3.0.0 on Eden Stable.

> **IMPORTANT: THIS IS THE 900P DOCKED PRESET. ENABLE DOCKED MODE IN EDEN BEFORE PLAYING.**

## What is included

- `totk-ultracam-3.0.0-900p-docked-exefs-v1.1.0.zip` — unchanged UltraCam 3.0.0 ExeFS payload. Install it through TOTK's **Add-ons** manager.
- `totk-ultracam-3.0.0-900p-docked-config-v1.1.0.zip` — the separate 900p UltraCam configuration. Extract its `UltraCam` folder directly into Eden's existing virtual `sdmc` root.
- `totk-eden-stable-900p-docked-v1.1.0.ini` — my updated Standard/Stable Eden per-game preset. Back up first and import it through Eden's per-game **Import Config** action.

The ExeFS add-on, SDMC configuration, and Eden INI have different destinations. The [complete installation guide](https://github.com/MPDERPER/totk-android-ultracam-ports#installation-guide--read-this-first) explains every step.

## Tested configuration

- Resolution: **1600 × 900**
- Required emulator profile: **Docked Mode**
- UltraCam: **3.0.0**
- Shadow configuration: **`ShadowResolution = 512`**
- Render distance: `5000`
- FOV: `45`
- Dynamic FPS: enabled
- FPS target: `60`
- FSR: enabled
- FXAA: disabled
- Handheld override: disabled, with the supplied 1280 × 720 handheld values preserved

The shadow value is the actual supplied and tested setting. I did not change it to the historical 8192 maximum. Higher rendering resolution and shadow settings can increase GPU workload and memory use.

## Installation summary

1. Install the ExeFS ZIP through TOTK's Eden **Add-ons** manager and enable UltraCam 3.0.0. Enable only one UltraCam executable version.
2. Extract the configuration ZIP's `UltraCam` folder into Eden Stable's existing virtual `sdmc` root. The final INI must be `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini`.
3. Import the Stable Eden INI through the per-game **Import Config** action. Review every imported value and select a GPU driver compatible with your device.
4. Enable **Docked Mode**, restart Eden, and verify that UltraCam reports 1600 × 900 and `ShadowResolution = 512`.

Do not install the SDMC configuration through Add-ons. Avoid `sdmc/sdmc/UltraCam/...` and `sdmc/UltraCam/UltraCam/...` duplicated paths.

## Compatibility

I recommend UltraCam 3.0.0 for TOTK 1.4.1 and 1.4.2. Historical upstream metadata lists 1.1.0–1.2.1 and 1.4.0–1.4.2 for 3.0.0. My Android observations are separate from those upstream listings. I encountered repeated crashes on 1.4.3, but that device-specific observation is not a universal incompatibility claim.

The Stable preset contains a GPU-driver path from my Snapdragon 8 Gen 2 setup. Importing the INI does not install that driver. Standard Eden may not support every Nightly-specific key retained in the export, so check the settings that your build actually exposes.

## Reported performance

I tested this 900p Docked preset on my **AYN Thor Max with Snapdragon 8 Gen 2 / Adreno 740**. Compared with my 720p configuration, I observed approximately **5 FPS lower performance in comparable overworld gameplay**, while shrines still reached approximately **60 FPS**.

These are my observations, not independently reproduced benchmarks or guarantees. They do not prove that the difference comes exclusively from resolution or shadows, and they do not establish sustained native 60 FPS across every scene or device.

## 720p alternative

The existing [v1.0.0 720p release](https://github.com/MPDERPER/totk-android-ultracam-ports/releases/tag/v1.0.0-android-ports) remains available as the performance-focused option.

## Credits and licensing

UltraCam and NX Optimizer were created by [MaxLastBreath](https://github.com/MaxLastBreath/nx-optimizer). I performed the Android configuration, adaptation, packaging, optimization, and testing with technical assistance from ChatGPT. The executable payload is unchanged and is redistributed under the upstream CC BY-NC 2.0 notice. This project does not imply endorsement by Nintendo, Eden, or MaxLastBreath.

No ROM, game update, firmware, keys, emulator binary, GPU-driver binary, or Nintendo game assets are included.

## SHA-256

```text
b42a413ac0e361f0927c69374ef1daf29221aa36662d8af60f2c8de9f646924b  totk-eden-stable-900p-docked-v1.1.0.ini
7960eb17fb1c60f0a32ceb397c57754811857fa4050d96b22bd0068dc77e20ca  totk-ultracam-3.0.0-900p-docked-config-v1.1.0.zip
57d802bef11afc2c98f83b79f820a7e89e10dfcbcea3930e0808b4ab7ed3f319  totk-ultracam-3.0.0-900p-docked-exefs-v1.1.0.zip
```
