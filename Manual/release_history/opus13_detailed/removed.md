##### Directory Opus 13 - Detailed release notes

# Removed Functionality

- Flickr sync is no longer supported.
- Removed support for display of "Compatibility Files" merged into folders below Program Files and similar:
  - This is an outdated concept which File Explorer has also dropped. Dates back to the introduction of UAC in Windows, when a lot of software still stored settings under Program Files. Rarely used today.
  - The \<ib:inline-code\>`Set COMPATIBILITYFILES`\</ib:inline-code\> command has been removed.
  - The \<ib:inline-code\>`Go COMPATIBILITYFILES`\</ib:inline-code\> command still works (toggles between the normal folder and corresponding Compatibility Files folder).
- Removed options to make various Opus windows on-top. (With UI adjustments to help. For example, Preferences and Customize can be saved, cancelled or brought to the front via Lister titlebars without having to go back to their windows.)
- The "slide-out navigation" buttons have been removed.
- The ability to change the root of the folder tree has been removed. (It generally confused people, and tree contents are now much more configurable, so it shouldn't be needed.)
- The \<ib:inline-code\>`Go ROOTTREE`\</ib:inline-code\> and \<ib:inline-code\>`Set TREEROOT`\</ib:inline-code\> commands have been removed - new Folder Tree Contents Preferences make them unnecessary for most people. We may add these back in the future.
- The \<ib:inline-code\>`Go LIMITPATH`\</ib:inline-code\> command and associated functionality to limit a Lister to specific locations has been removed.
- Support for Windows Vista has been dropped. Windows 7 is the minimum now.
- Support for 32-bit Windows has been dropped.
- There is no longer a separate "Light/Lite" (as in simplified) version of Opus. (Light users can still upgrade to 13; the upgrade process will treat them the same as Pro users.)

------------------------------------------------------------------------

Next: [Directory Opus 13 - Tips for Upgrading from Opus 12](/Manual/release_history/opus13_upgradetips.md)
