##### Directory Opus 13 - Detailed release notes

# Metadata

- General:
  - Video and Audio bitrates are now reported if the true bitrate is unknown but a nominal bitrate is known.
  - Added "Preferences / File Operations / Metadata / Save descriptions to internal file metadata if possible" option (on by default). If turned off, Opus won't try to save descriptions to internal metadata unless a description is already set there. Instead, it will go straight to NTFS comments or a descript.ion file, depending on config.
- Video metadata:
  - Overhauled video metadata, now based on the industry-standard MediaInfo library, with optional fallback on the Windows Shell properties system.
  - Works with many more video formats than before, and is independent of Windows and shell extension DLLs, which have proven unreliable.
  - Better reporting of audio and video codecs.
  - New columns include High Dynamic Range (HDR), Video Languages, Audio Languages, Subtitle Languages, All Languages (merges the other three language lists), Video Stream Count, Audio Stream Count, Subtitle Count.
  - The general Description column now indicates if a video is HDR, and also if it use frame-packed 3D.
  - Note that the metadata editor is not affected by these changes, and still works as before, with a dependence on Windows, since it needs to read and write values, not just read them. These changes affect file display columns, info tips, and filters (e.g. Find \> Advanced), but not the metadata panel.
  - Aspect Ratio column can be set to report Display Aspect Ratio. This may differ from the raw x/y pixel ratio for things like anamorphic DVDs where the raw pixels are stretched more horizontally than vertically. It's off by default, and configured via the Video & Audio plugin: "Adjust dimensions for non-square pixels".
  - Added extra data to video info tips. (If updating: Settings \> File Types, expand File Type Groups, right-click Movies and choose Reset to Defaults.)
  - MOV: Fixed release date not populating for some MOV files.
  - MP4: Fix for some MP4 metadata fields being written but not read back.
- Audio metadata:
  - WAV: Added support for displaying and editing ID3v2 tags in WAV files. (Note: WAV metadata isn't very standardized. Not all software uses ID3v2 with WAV.)
  - FLAC: Workaround toi avoid trashed tags due to bug in the Windows FLAC metadata component.
  - APE: Fix for editing APE tags that couldn't be fully parsed.
- Metadata editors:
  - (Configured via Preferences / File Operations / Metadata / Editor.)
  - New option, "Decimal geocoordinate editing", makes the editor use decimal GPS coordinates. (Doesn't affect file display columns.)
  - New option, "Add to multi-value fields by default, when multiple files are selected":
    - When on, and multiple files are selected, typing into multi-value fields like "tags" will add what you type to each file's unique tags.
    - When off, each file's old tags will be removed and replaced by just what you've typed. (This is the old behavior.)
    - In either mode, you can prefix with + to always add a single tag, - to remove one, or = to set all files to only what you type.
  - When editing the "tags" field, a suggestions popup can appear with a menu of recent tags:
    - Type a prefix or push Ctrl+Space to make it appear.
    - Turn off via "Show popup tag history" checkbox.
    - If "Include read tags as well as written" is on, tag suggestions will be collected from existing files. When off, only tags you type yourself will be remembered.
  - You can now edit the music genre list: Preferences / File Operations / Metadata Editing / Music Genres.
  - Renamed "Color space" to more correct "Color model" in various places.
  - Metadata editor now lets you click Apply after typing in a field, while that field still has focus.
  - Fixed error when clearing metadata from a file on a FAT32 volume.
  - Fixed extra refresh of metadata editor a moment after saving, which got in the way of making a quick second edit of the same file.
  - Aperture and F-number now show values rounded to one decimal place, consistent with file-display columns and most other software.
- Commands:
  - `SetAttr DEFAULTADDMULTI`
  - The Preferences option does not affect the behaviour of the SetAttr command. Instead, add the DEFAULTADDMULTI argument for the new behaviour.
  - If opening the standalone metadata editor, DEFAULTADDMULTI=no lets you override the Preferences option if it is on.
  - The "colormodel" keyword replaces "colorspace" (both still work, for compatibility).

------------------------------------------------------------------------

Next: [columns](/Manual/release_history/opus13_detailed/columns.md)
