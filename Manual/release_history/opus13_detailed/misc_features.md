### Directory Opus 13 - Detailed release notes

# Miscellaneous Features

- Preferences / Miscellaneous / Privacy: Central place to clear or turn off various suggestion and history ("MRU") lists based on previous actions and files.
- Preferences / Launching Opus / Startup / Backup open Listers automatically: Periodic backup of open windows and tabs, in case of crash, power-cut, etc.
- The simple audio player (`Play` command) has wider format support.
- Create Folder dialog has a popup suggestions list, generated from previous folder names. Displays automatically when typing. Push Ctrl+Space to force it to open.
- Added tool to securely erase empty space on a hard drive.
  - *Command:* `Delete ERASEEMPTYSPACE` -- Optional args are drive letter and number of passes, e.g.: `Delete ERASEEMPTYSPACE D:,passes:2`
- Custom titles/labels for Listers, viewers and folder tabs can now hide sections when all tokens inside are empty:
  - Add "%!" around optional text.
  - //<Example://> `%!%T - %!Directory Opus` -- If the %T expands to nothing, the result will be "Directory Opus" and not " - Directory Opus".
- Buttons/toolbars in Preferences and various other dialogs now add labels to buttons when there is room. Dynamically switch to icon-only buttons if window too narrow.
- Faster startup on systems with very large File Collections. (Initial load will be slow, converting the data into a new format which makes subsequent loads much faster.)
- Listers remember how they were opened, adding the information to the status info/padlock tooltip (same place the Folder Format info is shown). Can be useful for tracking down external triggers that open unwanted folder windows.
- Added option to set the maximum number of undo entries (Preferences / File Operations / Options).
- You can now generate a "toolbar glossary" which lists everything on the default toolbars and menus (and a few other things) in two languages, side-by-side. This can be useful if you need to know the name of something in another language when searching the manual or help forum.
- Stored Queries can now set the various options for the different search engines via a popup menu.
- Added high DPI versions of custom mouse cursors, and replaced some icons with high-DPI or vector versions, for better scaling/antialiasing.
- When pasting image or text data into a new file, the "Clipboard Image.bmp" or "Clipboard Text.txt" filenames can now have a YYYY-MM-DD HH-MM-SS datestamp prefixed for natural sorting by date/time. (Preferences / Miscellaneous / Advanced \[Behavior\]: clipboard_datestamps).
- Added user interface for sending crash dumps. Accessed via Help menu, or `Help CRASHDUMPS` command.
- Added commands to the Lister menu (accessed by clicking the main window icon):
  - "Show Default Toolbars" and "Reset Default Toolbars", to help in situations where no toolbars are visible.
  - Revived "Listers" sub-menu, when more than one window is open. Lets you select other Listers, as well as tile, cascade, etc. the windows.
  - "Undo Tile/Cascade" to put windows back where they were after a tile or cascade.
    - *Command:* `Set LISTERCMD=UndoTileCascade`
- Separators in the Favorites list can now be turned into named headings, which are displayed in the Favorites menu.
  - When you add a new separator in Preferences, Opus will ask you for the text for the heading. Leave it blank to create a traditional separator.
  - Right-click or double-click on an existing separator/heading to edit it.
- You can now specify the default PowerShell executable (Preferences / Miscellaneous / Advanced / powershell_exe). For example, to make commands which open PowerShell use PowerShell 7 instead of Windows PowerShell.
  - You can still override this for individual buttons using the CLI command's EXEC argument.
- `DOpusRT.exe /cmd` (used for running Opus commands from outside of Opus) has a new, clearer syntax, allowing future expansion in a cleaner way:
  - `/cmd` by itself is unchanged
  - `/cmd:viewer` -- new way of saying /vcmd
  - `/cmd:active` -- new way of saying /acmd
  - `/cmd:active,thisdesktop` -- Looks for the active Lister, but only on the current virtual desktop.
  - The old `/acmd` and `/vcmd` still work, to avoid breaking existing things, but we recommend the new syntax for new things.
- Windows saved and re-opened across restarts now remember their original layout names, if any.
- Option to automatically check for and install updates to your certificate. (Can be on demand via Help \> Licence Manager, or on a schedule.)
- Config backup names now include the time (not just the date), and backups include sub-folders of `/iconsets`.

------------------------------------------------------------------------

Next: [Miscellaneous Fixes & Workarounds](/Manual/release_history/opus13_detailed/misc_fixes.md)
