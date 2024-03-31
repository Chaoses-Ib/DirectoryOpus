### Directory Opus 13 - Detailed release notes

# Image Converter

- Redesigned UI.
- Presets system: Load and save settings in the UI to named presets.
  - Presets can be accessed via right-clicking an image file.
  - If you don't see the new context menu: Settings \> File Types \> File Type Groups \> right-click Images \> Reset to Defaults.

- Added crop option. Can crop to a specified size, or aspect ratio.
- You can now edit the list of resizing presets.
- Added Lossless JPEG option to UI (previously only available via command).
- Added choice of replacing existing files (with or without asking first), saving new copies, or saving results to the destination folder.
- Added option for wildcard or regular expression renaming of output files.
- Reports aspect ratios next to dimensions.
- Improved error reporting.
- Workaround for conversion failing on photos with excessively large "Google Camera" metadata. If the data is too large, it will now be stripped from the destination.
- Commands:
  - `Image CONVERT PRESET="My Preset"` -- Or "!default" to open the dialog with factory defaults.
  - `Image CONVERT PRESET=!list` -- Generates a list of presets, for toolbars/menus.
  - `Image CONVERT PRESET=!menu` -- If no presets, just "Convert Image"; else a sub-menu of presets with "Convert Image" at the top.
  - `Image CONVERT CROP=...` -- Crop an image from the command-line, or specify CROP=no to override a preset.

------------------------------------------------------------------------

Next: [labels](/Manual/release_history/opus13_detailed/labels.md)
