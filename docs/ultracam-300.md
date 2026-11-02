# UltraCam 3.0.0 Android package

The 3.0.0 asset contains unchanged upstream `main.npdm` and `subsdk3` files matching MaxLastBreath’s `manager-3.2.0` tag. Its separate configuration belongs at `sdmc/UltraCam/TOTK/Config/`.

Historical 3.0.0 metadata lists TOTK `1.1.0`, `1.1.1`, `1.1.2`, `1.2.0`, `1.2.1`, `1.4.0`, `1.4.1`, and `1.4.2`. In my Android tests, the FPS unlock and working graphical optimizations remained operational on 1.4.1 and 1.4.2. I therefore recommend 3.0.0 for these newer updates.

I observed repeated crashes on 1.4.3. That is a limitation of my device, Eden build, driver, and configuration combination, not proof of universal 1.4.3 incompatibility.

## Installation

Install the ExeFS ZIP through TOTK’s **Add-ons** screen. Separately extract the configuration ZIP to Eden’s virtual SD-card root so these files exist:

```text
sdmc/UltraCam/TOTK/Config/maxlastbreath.ini
sdmc/UltraCam/TOTK/Config/PaletteCFG.json
```

Do not install the configuration ZIP through Add-ons and do not enable 2.7.1 simultaneously. In my tested controller configuration, hold **ZL + ZR** and press **L3** to open the menu.

See [Installation](installation.md), [Configuration](configuration.md), and [Compatibility](compatibility.md).
