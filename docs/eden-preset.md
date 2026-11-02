# Eden Nightly per-game preset

`0100F2C0115B6000.ini` is an optional TOTK emulator preset. It is separate from UltraCam’s `maxlastbreath.ini`.

## Preserved tested values

```ini
[Cpu]
use_custom_cpu_ticks=true
cpu_ticks=21000

[Renderer]
frame_gen=true
frame_gen_multiplier=2
frame_gen_target_rate=0
frame_gen_flow_scale_auto=false
frame_gen_flow_scale=50
frame_gen_queue_target=1
```

These values correspond to 21,000 custom CPU ticks, fixed 2× frame generation, 50% motion-estimation resolution, and Balanced (1 frame). They remain unchanged for reproducibility.

## Import procedure

1. Back up your existing TOTK per-game settings.
2. Open TOTK’s properties in Eden Nightly.
3. Use the supported **Import Config** action and select `0100F2C0115B6000.ini`.
4. Review CPU, graphics, and frame-generation settings.
5. Recheck the selected GPU driver and restart Eden.

## Driver path and provenance

The saved path references `TurnipZ-0.3.0.zip` under the original Eden Nightly app-data directory:

```text
/storage/emulated/0/Android/data/dev.eden.eden_emulator.nightly/files/gpu_drivers/TurnipZ-0.3.0.zip
```

That path is installation-specific. Importing the preset does not install TurnipZ or any other driver. TurnipZ 0.3.0 was used for the published benchmark readings.

I later tested a driver from StevenMXZ’s Turnip v27.0.0-R1 release and experienced smoother gameplay, but did not preserve the exact ZIP or a verified Android path. The preset therefore keeps the original path. Install and select a newer compatible driver manually instead of editing the file to a guessed location.

The 21,000 tick value and other device-specific options may be unstable elsewhere. Back up first and revert individual values or reset per-game settings if needed.
