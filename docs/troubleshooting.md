# Troubleshooting

## The mod does not load

Confirm that exactly one UltraCam version is enabled and that `exefs` is directly below the installed mod folder. Disable conflicting `main.npdm`, `subsdk3`, FPS, resolution, Dynamic FPS, and UltraCam mods. Check the exact game update and fully restart Eden.

## UltraCam 2.7.1 graphics work, but FPS stays near 30

On TOTK 1.4.1 and 1.4.2, this matches my testing. The package can load, keep the game playable, and apply reduced render distance, FOV, and other graphics changes while its FPS unlock remains nonfunctional. Use UltraCam 3.0.0 for FPS unlocking on these newer updates. Adding a legacy RomFS INI does not guarantee that the old FPS patch will support 1.4.x.

## The configuration is ignored

For 3.0.0, verify `sdmc/UltraCam/TOTK/Config/maxlastbreath.ini`. Avoid `sdmc/sdmc/UltraCam`, `UltraCam/UltraCam/TOTK`, an unextracted ZIP, or installing the INI through Add-ons.

For 2.7.1, the original customization location is `romfs/UltraCam/maxlastbreath.ini`, but this release is ExeFS-only. Its base-game FPS behavior can work without a separately supplied INI; the 3.0.0 SD-card INI is not interchangeable.

## The game crashes

I repeatedly saw crashes on 1.4.3 in my setup. This is not a universal incompatibility claim. Record the game update, Eden build, GPU driver, device, and enabled mods. Test with one UltraCam version, restore the previous driver, lower device-sensitive settings, and monitor temperature.

## Graphics are corrupted or performance is worse after changing drivers

Return to the previous working or system/default driver and restart Eden. The A8xx `Turnip_Gen8_V38` archives are not the default for Adreno 740. For the StevenMXZ v27.0.0-R1 release, the regular package is the expected 6xx/7xx starting point; the OneUI archive is specialized. Follow current developer notes and see [GPU drivers](gpu-drivers.md).

## Imported preset selects TurnipZ or an unavailable path

The released preset preserves the original TurnipZ 0.3.0 Android path. Importing it does not install a driver. Install a compatible driver through Eden’s GPU Driver Manager, select it manually after importing, and restart. Do not replace the stored path with a guessed path from another Android installation.

## Frame generation looks smooth but the counter is confusing

The preset enables fixed 2× frame generation. Generated output frames are separate from native game-rendered frames, and the counter’s treatment of them is unknown. Judge game speed, frame pacing, latency, and visual artifacts separately. See [Frame generation](frame-generation.md).

## Restore defaults

Restore the per-game configuration you backed up, reset TOTK’s settings, disable the add-on, or return individual options to global/default. Custom CPU ticks, driver choice, asynchronous options, texture overrides, and frame generation are device-sensitive.
