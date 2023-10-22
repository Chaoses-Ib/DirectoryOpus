##### Directory Opus 13 - Detailed release notes

# Miscellaneous Fixes & Workarounds

- Fixed custom scrollbar colors being reset after certain events resetting (e.g. Remote Desktop connection).
- Fixed problem with New -\> Rich Text Document not creating a valid empty RTF file.
- Improved handling of icons that take a long time to retrieve (e.g. due to shell extenions or network drives).
- Workaround for some issues with MTP devices, where the related Windows component freezes when asked for icons.
- WSL support now works correctly when the current folder is a \`\\wsl\$\` or \`\\wsl.localhost\` path (e.g. \`CLI DOSPROMPT=wsl\`, or \`\|\` in FAYT to run a Linux command).
- Added workaround for the width of columns in the Digital Signatures tab of Properties dialogs:
  - Due to a bug in Windows which Microsoft have never fixed, the columns use a fixed size which doesn't scale with DPI. Affects File Explorer as well.
  - Opus will now resize the columns for high DPI displays, so you don't have to manually resize them every single time while screaming "WHY!?".
  - Only affects Properties dialogs opened in-process, not ones opened via other software (e.g. File Explorer), or via out-of-process context menus.
- Added workaround for Shell folder thumbnails which sometimes generated with opaque, black backgrounds:
  - This is a very old bug in Windows. Affects File Explorer as well.
  - Opus now detects when it happens and uses an algorithm to remove the black background. The result isn't perfect, but looks a lot better.
  - Only affects thumbnails in Opus. File Explorer will still randomly show black borders around folders until Microsoft fix their bug, probably shortly after the heat death of the universe.
- Fixed some issues with context menus for shortcuts in newer versions of Windows.
- Improved how the path field's auto-completion works when typing the name of FTP Address Book branches.
- \`Go @BranchName\` and \`Go FTPSITE=BranchName\` now work with FTP Address Book branches, displaying the list of sites (and sub-branches) under that branch in the file display. (Already worked with actual FTP sites from the Address Book.)
- \`Go @SiteName NEWTAB=findexisting\` now correctly finds existing tabs showing the specified FTP site.

------------------------------------------------------------------------

Next: [Miscellaneous Commands](/Manual/release_history/opus13_detailed/misc_commands.md)
