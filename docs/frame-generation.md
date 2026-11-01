# Frame generation

The preset enables Eden's frame interpolation at a fixed 2× multiplier.

- **Rendered FPS** counts frames produced by the game/emulator rendering pipeline.
- **Generated output** includes interpolated frames inserted between rendered frames.

Generated frames can improve perceived motion smoothness, but they do not make the game simulation run faster. They can add GPU cost, input latency, and interpolation artifacts.

At 2×, Eden attempts to display two output frames for each rendered frame. This does not guarantee that a 30 FPS source becomes a perfectly paced 60 FPS presentation. Timing, GPU capacity, display refresh, source cadence, and emulator implementation still matter.

The 50% motion-estimation value runs the optical-flow pass at half the output resolution. Eden's own interface describes lower values as saving GPU time. The tradeoff can be lower interpolation quality. No specific FPS gain is claimed here.

The benchmark counter's treatment of generated frames was not established from supplied recordings or logs, so the reported 35/40/45/55 FPS readings remain **observed readings of unknown native/generated composition**.
