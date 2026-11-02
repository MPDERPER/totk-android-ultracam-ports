# UltraCam 2.7.1 Android package

The 2.7.1 asset contains unchanged upstream `main.npdm` and `subsdk3` files inside an Eden-compatible ExeFS folder. They match MaxLastBreath’s `manager-3.1.0` tag.

## Version support and observed behavior

Historical 2.7.1 metadata lists TOTK `1.1.0`, `1.1.1`, `1.1.2`, `1.2.0`, and `1.2.1`. It does not list 1.0.0 or 1.4.x.

- On the unupdated 1.0.0 base game, I observed the ExeFS-only package loading with its 60 FPS unlock working.
- On 1.4.1 and 1.4.2, the package still loaded and the game remained playable. Reduced render distance, modified FOV, and other visible graphics changes worked, but the FPS unlock did not; gameplay remained around 30 FPS.
- I encountered repeated crashes on 1.4.3 in my Android setup.

The 1.4.1/1.4.2 result is **partial functionality**, not total incompatibility. It is consistent with a version-specific FPS patch issue, but this project has not proved the binary-level cause. Use UltraCam 3.0.0 for FPS unlocking on those newer updates.

## Installation and configuration

Install the package through TOTK’s **Add-ons** section and enable only this UltraCam version. The executable structure is:

```text
UltraCam 2.7.1/
└── exefs/
    ├── main.npdm
    └── subsdk3
```

The original customization path is `romfs/UltraCam/maxlastbreath.ini`. This release does not include a legacy 2.7.1 RomFS INI. The ExeFS-only package can still perform its built-in behavior, as shown by my base-game test. The legacy INI is for customization; it does not guarantee that the old FPS patch will work on 1.4.x. Do not use the 3.0.0 SD-card configuration with 2.7.1.

See [Installation](installation.md) and [Compatibility](compatibility.md).
