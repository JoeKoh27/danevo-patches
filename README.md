# DanceEvolution Arcade — Spice2x Patches

A collection of runtime JSON patches for **DanceEvolution Arcade**, including native 1080p rendering, song license region selection, Omnimix support, and capture options.

Patches are applied by Spice2x in memory. The original game DLLs can remain untouched.

## Supported build

| Item | Supported value |
| --- | --- |
| Game | DanceEvolution Arcade |
| Game code / datecode | `KDM-2016080100` |
| Target DLL | `gamekdm.dll` |
| PE identifier | `KDM-5784d760_1d897b` |
| Patch filename | `KDM-5784d760_1d897b.json` |

These patches target this specific DLL build. The datecode alone does not guarantee compatibility.

## Import into Spice2x

1. Open **spicecfg.exe** and select DanceEvolution Arcade.
2. Open the **Patches** tab and click **Import from URL**.
3. Paste this URL:

   ```text
   https://joekoh27.github.io/danevo-patches/
   ```

4. Click **Import**, then enable the patches you want.

Use the base URL above. Spice2x automatically appends the filename for your DLL build.

### Manual installation

1. [Download the patch JSON](https://raw.githubusercontent.com/JoeKoh27/danevo-patches/main/KDM-5784d760_1d897b.json).
2. Save it in Spice2x's `patches` folder, normally `patches/` in your launch directory.
3. Keep the filename exactly `KDM-5784d760_1d897b.json`.
4. Open the **Patches** tab and select the options you want.

## Available patches

| Patch | What it does |
| --- | --- |
| **Kinect bypass** | Bypasses the physical Kinect boot requirement and player-presence checks during calibration. |
| **Timer Freeze** | Freezes the countdown timers in music select and difficulty select. |
| **60 FPS limiter** | Limits the game to 60 FPS; useful with high refresh rate monitors. |
| **Attract Mode - Full Song Pool** | Selects attract-mode songs from the full live song pool, skipping tutorial, null, and unavailable entries. |
| **Demo MASTER** | Changes attract/demo chart previews to MASTER difficulty. Normal gameplay difficulty selection remains untouched. |
| **Clean Capture - Hide gameplay visuals** | Hides CREDIT/PASELI and in-game UI, and mutes note hit sounds. Use with STEALTH difficulty to hide the notes. Enable before launch; do not toggle during gameplay. |
| **Omnimix Patch** | Required when using the compatible DanceEvolution Omnimix Setup. |
| **Native 1080p Render** | Renders at 1920×1080 with adjustments to UI positioning. Original 2D artwork, including HUD/UI assets and song jackets, is not upscaled. |
| **Fake Region** | Overrides the region used for song licence checks without changing the UI language. Select Japan to unlock all songs. |

### Fake Region choices

| Choice | Region |
| --- | --- |
| **Default** | Original behaviour |
| **Japan (J)** | Japan |
| **Asia (A)** | Asia |
| **China (C)** | China |
| **Korea (K, experimental)** | Korea |

**Japan has been tested offline with the final-update song set and makes all songs available for play without a network.**

The override affects song license checks. The actual region and UI language continue to follow `eamuse-config.xml`.

### Omnimix and 1080p notes

- The JSON does not include Omnimix song assets or the required external hooks. Use the **Omnimix Patch** with the matching Omnimix installation.
- The **Native 1080p Render** patch changes rendering and positioning; it does not replace or upscale the original 2D assets.
- Configure the display/window for 1920×1080 when using the 1080p option.
- Enable patches before launching the game, particularly rendering and clean-capture options.

## Updating

Import from the same URL again to download the latest JSON, review your selections, and restart the game.

**Auto Apply applies your saved local patches; it does not automatically download repository updates.**

## Troubleshooting

- **HTTP 404 during import:** Check that you entered the base URL and that your DLL's PE identifier is supported.
- **Invalid JSON during import:** Use the raw import URL above rather than a GitHub file-view page or the complete JSON-file URL.
- **Patches do not appear or cannot be applied:** Confirm that your DLL matches the supported build. A previously modified DLL may not match the expected original bytes.
- **Omnimix songs or previews are missing:** Check the separate Omnimix assets and hooks; this repository supplies the JSON patches.

## Links

- [Spice2x](https://spice2x.github.io/)
- [Spice2x patching documentation](https://github.com/spice2x/spice2x.github.io/wiki/Patching-DLLs-(hex-edits))
- [Report an issue](https://github.com/JoeKoh27/danevo-patches/issues)

