# UltraCam configuration

This page documents only values present in the supplied UltraCam 3.0.0 `maxlastbreath.ini`.

| Section / option | Value | Practical meaning |
| --- | --- | --- |
| `Resolution.Width`, `Height` | `1280`, `720` | 720p internal target. |
| `Handheld.Width`, `Height` | `1280`, `720` | 720p handheld values. |
| `OverrideHandheld_Resolution` | `True` | Requests the configured handheld resolution. |
| `UltraCamFPS.MaxFPS` | `60.00` | Gameplay frame-rate target/cap. |
| `UltraCamFPS.MenuFPS` | `60` | Menu frame-rate target. |
| `UltraCamFPS.MovieFPS` | `30` | Movie frame-rate target. |
| `UltraCamFPS.DynamicFPS` | `True` | Enables UltraCam's dynamic frame-time/game-speed handling. |
| `UltraCamFPS.Buffer` | `8` | UltraCam FPS buffer value. |
| `ShadowResolution` | `206` | Low shadow resolution with a quality tradeoff. |
| `RenderDistance` | `5000` | Reduced render distance; distant detail may be reduced. |
| `Fov` | `45.00` | Narrower field of view. |
| `FSR` | `True` | Enables the named UltraCam FSR option. |
| `FXAA` | `False` | Disables the named UltraCam FXAA option. |
| `QualityImprovements` | `True` | Enables UltraCam's named quality-improvement behavior. |
| `AmbientOcclusion` | `Off` | Disables ambient occlusion. |
| `Bloom` | `Off` | Disables bloom. |
| `ScreenSpaceRefl` | `Off` | Disables screen-space reflections. |
| `VolumetricFog` | `Off` | Disables volumetric fog. |
| `GameTextures`, `RSDB` | `1.00`, `1.00` | Default-scale heap values in the supplied preset. |
| `IsTimeSlower` | `False` | Slow-time behavior is disabled. |
| `TimeSpeed` | `1.00` | Normal time-speed multiplier. |
| `TriggerWithController` | `True` | Enables controller access to UltraCam controls. |
| `DisplayAverage`, `DisplayLows`, `DisplayMax`, `DisplayMs`, `DisplayGraph`, `Overlay` | `True` | Enables the supplied on-screen performance display options. |

The file does not contain `RemoveDepthOfField`, `RemoveLensflare`, grass controls, a separate emulator-scale key, or a benchmark selector, so this repository does not claim those options are part of this 3.0.0 preset. The four shader toggles were recognized in my testing, but their individual performance effects were not independently measured.

The accompanying `PaletteCFG.json` keeps the manager disabled and preserves neutral/default color values. It is included because it was part of the supplied working configuration folder.
