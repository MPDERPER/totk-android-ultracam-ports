# Provenance

## UltraCam 2.7.1

Source: MaxLastBreath/nx-optimizer, tag [`manager-3.1.0`](https://github.com/MaxLastBreath/nx-optimizer/tree/manager-3.1.0), path `src/PatchInfo/Tears Of The Kingdom/UltraCam/exefs/`.

| File | SHA-256 |
| --- | --- |
| `main.npdm` | `d593a80e5e53f8603afab0655af31bac0aa37ebf8ab8e205017e38b581d9a006` |
| `subsdk3` | `930e4e995239bb40a4f68fb1a237bcf1b28aa9ce0a581533f8a02a92f76472a6` |

## UltraCam 3.0.0

Source: MaxLastBreath/nx-optimizer, tag [`manager-3.2.0`](https://github.com/MaxLastBreath/nx-optimizer/tree/manager-3.2.0), path `src/PatchInfo/Tears Of The Kingdom/UltraCam/exefs/`.

| File | SHA-256 |
| --- | --- |
| `main.npdm` | `d593a80e5e53f8603afab0655af31bac0aa37ebf8ab8e205017e38b581d9a006` |
| `subsdk3` | `3273a1f6cf5af36a5135da74ced66e292e4655174807e883ab4408b73a636fb9` |

All four supplied executable files were compared byte-for-byte with those upstream paths and matched. They were inspected and hashed, not executed.

## User-supplied configuration

| File | SHA-256 |
| --- | --- |
| `UltraCam/TOTK/Config/maxlastbreath.ini` | `57f3fe05f72b843e4d9ea98191c866e5e65a0fd7ce317eb9abeaeae30dc79adc` |
| `UltraCam/TOTK/Config/PaletteCFG.json` | `bfda17efb2d80244c7c5cd92d738f0c8881dd963886519f6c8cf491df81984af` |
| Original `0100F2C0115B6000.ini_2` | `1ebd0bd54e51a020c01632baff9699d8d8216198c0963f7ac437a480ec6cab54` |

Renaming the Eden preset does not change its bytes, so the release `.ini` has the same SHA-256.

## v1.1.0 900p Docked inputs

The UltraCam 3.0.0 ExeFS files in v1.1.0 are byte-for-byte identical to the v1.0.0 and upstream files listed above. The 900p configuration and Stable Eden export were supplied by MPDERPER and preserved without changing their tested values.

| File | SHA-256 |
| --- | --- |
| `UltraCam/TOTK/Config/maxlastbreath.ini` — 900p | `ffe9034aa7cf161bcd2650eac5654a448d6f12e1649b1ba8759bde85a71895a0` |
| `UltraCam/TOTK/Config/PaletteCFG.json` | `bfda17efb2d80244c7c5cd92d738f0c8881dd963886519f6c8cf491df81984af` |
| `totk-eden-stable-900p-docked-v1.1.0.ini` — corrected | `dee11281ddbfad6a5b78f99abd2e6adab414ab827f8284d789c3b57f3d662575` |

The corrected asset is based on the user-supplied `EDEN STABLE SETTINGS.ini` (`ab9fcccc986a52b0a791324fff84939511fb9aec52e524ea08826d913b3bc665` before the requested Docked Mode change). The published copy changes `use_docked_mode\default` from `true` to `false` and `use_docked_mode` from `0` to `1`. It preserves `scaling_filter = 0` and every other supplied value. The Eden INI format does not include a Nintendo title ID; a separately named byte-identical copy is used for BOTW at MPDERPER's explicit direction.
