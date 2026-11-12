# Research: Forza Horizon 4 on Apple Silicon

Updated 12/11/2026. Facts come from the FH5 research repo (public sections) and from read-only checks on 11/11/2026. This repo publishes no addresses, RVAs, function names, key names or provider DLL names of the third-party project (decisions.md, D-002).

## 1. What is installed on the test Mac

| Item | Value | Status |
|---|---|---|
| Mac and software | M4 Pro, 24 GB RAM. macOS 27.2 (26B123). CrossOver 26.3 (build 26.3.0.39832) | Proven (FH5 research.md, section 1) |
| FH4 patches in the `Steam` bottle | `kernelbase.dll` SHA-256 starts `313a9d07`. `d3d12.dll` starts `f3038fdc`. 7 environment keys with the `HB_` prefix are set in `cxbottle.conf`. A provider DLL is present | Proven (shasum, read of the config copy, 05/11/2026) |
| FH4 patch tool runs | The CrossOver `apple_gptk` folder holds 3 backups named `d3d12.dll.bak_fh4_archive_<date>-<time>`: 29/10/2026 14:15, 07/11/2026 15:41 and 09/11/2026 23:54. All 3 have the SHA-256 `02aa6734` (the stock file) | Proven (file names, shasum, 11/11/2026). That the patch tool made them is an inference from the name |
| `d3d12.dll` in the CrossOver `apple_gptk` folder | It is the FH4 proxy (`f3038fdc`) since 09/11/2026 23:54 | Proven (shasum, ls, 11/11/2026) |
| FH4 launch result today | No result is recorded here since the CrossOver changes of 05/11/2026 to 11/11/2026. The patch tool ran again on 09/11/2026 at 23:54, so Adam may have played FH4 after that. Adam reports on 12/11/2026 that FH4 works with the third-party patches | User-reported. Not proven here: no log or screenshot. To prove it: Adam starts FH4 from the original `CrossOver.app` in the `Steam` bottle |

## 2. What the third-party project claims (not verified here)

Source: its README, read on 12/11/2026. Each line is a claim of the author.

- A launch loop at boot is fixed.
- Stretched polygons (a vertex layout bug) are fixed.
- A crash in free roam is fixed.
- A memory leak while driving is fixed (V1.1).
- Drift zones finish and exit normally (V3).
- Online play and Xbox Live configuration work.
- It needs macOS 27 or newer and CrossOver 26.3 with D3DMetal 4. The author says not to apply the binaries to another CrossOver release.
- The author says that about 30% of textures still show faults.

## 3. FH4 and FH5 on one Mac

The FH4 patch is app-wide. It replaces `d3d12.dll` in the CrossOver `apple_gptk` folder, so every bottle that uses D3DMetal loads it. This clashed with the FH5 research (FH5 D-017 and D-022).

Since 11/11/2026 FH5 is set up to run from its own app copy, `/Applications/CrossOver (FH5).app`, in its own bottle. It has not run there yet. The original `CrossOver.app` and the `Steam` bottle were not changed by that install:

| Check | Result | Status |
|---|---|---|
| Original app `ntdll.dll` | SHA-256 `6dff64c0...` before and after | Proven (shasum) |
| Original app `d3d12.dll` | Still the FH4 proxy (`f3038fdc`) | Proven (shasum) |
| `Steam` bottle files | No file newer than a marker file made before the install. Dates of `user.reg`, `system.reg` and `cxbottle.conf` are the same | Proven (find, stat) |

Meaning: by design, and not tested in game, FH4 and FH5 no longer fight over the shared `d3d12.dll`, as long as FH5 always starts from the app copy. One shared item stays: both games can use the same Steam library folder on the external SSD. A file in the FH5 game folder does not touch the FH4 game folder.

## 4. Open

1. Does FH4 still launch and reach free roam from the original app? Needs Adam.
2. The license of the third-party project (decisions.md, open question 1).
