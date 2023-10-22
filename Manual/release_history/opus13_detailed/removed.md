##### Directory Opus 13 - Detailed release notes

# Removed Functionality

- Flickr sync is no longer supported.
- Removed support for display of "Compatibility Files" merged into folders below Program Files and similar:
  - This is an outdated concept which File Explorer has also dropped. Dates back to the introduction of UAC in Windows, when a lot of software still stored settings under Program Files. Rarely used today.
  - The \`Set COMPATIBILITYFILES\` command has been removed.
  - The \`Go COMPATIBILITYFILES\` command still works (toggles between the normal folder and corresponding Compatibility Files folder).
- Removed options to make various Opus windows on-top. (With UI adjustments to help. For example, Preferences and Customize can be saved, cancelled or brought to the front via Lister titlebars without having to go back to their windows.)
- The "slide-out navigation" buttons have been removed.
- The ability to change the root of the folder tree has been removed. (It generally confused people, and tree contents are now much more configurable, so it shouldn't be needed.)
- The \`Go ROOTTREE\` command has been removed - new Folder Tree Contents Preferences makes it unnecessary for most people.
- The \`Go LIMITPATH\` command and associated functionality to limit a Lister to specific locations has been removed.
- Support for Windows Vista has been dropped. Windows 7 is the minimum now.
- Support for 32-bit Windows has been dropped. (At least initially. We can add it back if people need it, but we doubt anyone is still using 32-bit Windows.)
- There is no longer a separate "Light/Lite" (as in simplified) version of Opus. (Light users can still upgrade to 13, of course. Exact upgrade pricing/discounts TBD.)
