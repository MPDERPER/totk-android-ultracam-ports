# Troubleshooting

## UltraCam does not launch

Confirm that exactly one version is enabled and that `exefs` is directly below the installed mod folder. Disable conflicting `main.npdm`, `subsdk3`, FPS, resolution, and Dynamic FPS mods. Check the game update and fully restart Eden.

## UltraCam launches but settings do not apply

For 3.0.0, verify `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini` and avoid an extra nested `sdmc` folder. For 2.7.1, remember that this release does not include the required legacy RomFS configuration.

## The game runs in slow motion

Check Dynamic FPS, `IsTimeSlower=False`, `TimeSpeed=1.00`, emulator speed limits, the FPS target, and conflicting timing mods. Restore the supplied values before experimenting.

## Repeated crashes

Check the TOTK update first. I repeatedly saw crashes on 1.4.3, while versions through 1.4.2 worked in my setup. Also test Eden's system driver, disable other mods, clear only appropriate shader caches when justified, lower risky custom settings, and monitor temperature.

## Graphical corruption

Restore the system/default GPU driver, then test without color grading and other graphics overrides. Driver behavior, shader compilation, emulator regressions, and incompatible mod settings can all cause artifacts.

## Frame generation does not work

Confirm your Eden build exposes frame generation, the setting is enabled, target rate is fixed, multiplier is 2×, and the device supports the feature. Generated frames may be unavailable or too expensive on some hardware.

## Imported configuration does not recognize TurnipZ

The saved path belongs to the original device. Install TurnipZ 0.3.0 separately through Eden's GPU Driver Manager and select it manually after importing.

## The device is unstable after import

Restore the configuration you exported before installation, reset TOTK's per-game settings, or return individual options to global/default. Custom CPU ticks, driver choice, asynchronous options, and texture-processing overrides are device-sensitive.
