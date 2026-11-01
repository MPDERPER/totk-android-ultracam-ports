# Eden Nightly per-game preset

`0100F2C0115B6000.ini` is an exported per-game configuration for TOTK. The release copy preserves the supplied bytes; only the filename changes from `.ini_2` to `.ini`.

## Confirmed nondefault values

- Custom CPU ticks enabled at `21000`.
- Handheld mode (`use_docked_mode=0`).
- Frame generation enabled with multiplier `2`.
- Target rate `0`, mapped by current Eden Android resources to **Use a fixed multiplier**.
- Motion-estimation auto scale disabled; manual scale `50%`.
- Queue target `1`, mapped to **Balanced (1 frame)**.
- FSR sharpening `25`.
- GPU accuracy `1`, DMA accuracy `2`, and GPU fence behavior `1` are preserved as numeric values because UI mappings can change by build.
- ASTC acceleration `0`.
- Disk shader cache, reactive flushing, buffer history, optimized vertex buffers, asynchronous shaders, vertex-input dynamic state, synchronized memory operations, and GPU texture unswizzle are enabled.
- Color-grade shader enabled with brightness, contrast, and gamma `1.05`, saturation `1.25`.
- Android pipeline worker count `4`.
- Driver path references `TurnipZ-0.3.0.zip` under the original Eden Nightly app-data directory.

## Portability warning

The saved driver path is:

```text
/storage/emulated/0/Android/data/dev.eden.eden_emulator.nightly/files/gpu_drivers/TurnipZ-0.3.0.zip
```

That path is specific to the original Android installation. Importing the INI does not install the driver. Install TurnipZ separately, select it in Eden, import the preset, then recheck the active driver.

The preset may be unstable on different SoCs, drivers, Eden builds, or thermal conditions. The 21,000 tick value is the top of Eden's currently documented recommended range and can cause freezes on some systems. Back up first and revert individual values or reset per-game settings if needed.

“CPU Debug / FreeDeno” is retained as my informal description of the test setup. The exported INI proves custom CPU ticks but does not contain a `cpu_debug` key or Freedreno environment variables.
