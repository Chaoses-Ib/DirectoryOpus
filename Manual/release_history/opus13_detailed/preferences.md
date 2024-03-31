### Directory Opus 13 - Detailed release notes

# Preferences

- Due to the amount of new functionality, Preferences has been reorganized. Remember the search field if you can't find something!
- Many pages now have explanations at the top, providing an overview without going to the manual. These are translated into all supported languages. They can be hidden by clicking (i) at the top.
- Extra information about certain settings is provided in the UI itself, and there are links between related pages to help find things.
- Changes on some Preferences pages now take effect immediately, without having to click OK or Apply. We haven't done this with all pages (and it would be detrimental to some), but most cosmetic settings are covered. Lets you see how things look with less clicking. The Cancel button will still revert any unsaved changes.
- You can now flag Preferences pages by clicking the stars next to them in the page list. Those pages then appear at the top of the list for easy access.
- The File menu has moved to a "hamburger" icon at the top right. A new item within can generate the command to open the current page, allowing easy creation of buttons/hotkeys/etc. to open pages you use a lot.
- The Advanced Preferences page now has its own search field. It can also be filtered by category, and set to show only the settings you have changed.
- Layouts page now lets you edit the windows inside a layout, automating the process somewhat:
  - Select a layout and click Edit.
  - After a confirmation, any existing Listers are saved to a temporary layout. They are then closed, and the selected layout opens.
  - Make any desired changes to the Listers, then click OK.
  - The layout will be updated. Its windows will then close, and the previously opened windows will be restored.
  - (Of course, you can still do it the old way, by saving your current windows over an existing layout.)
- Preferences / Folders / Automatic Reading: Options to delay loading of folders can now be overridden for specific paths.
- The Scripts page has moved out of Preferences into a separate dialog. (See [Script IDE](script_ide.md).)
- In Viewer and Archive/VFS plugin lists, cog buttons appear next to plugins that support configuration.
- While the Preferences window is open, Lister and viewer windows have titlebar buttons to commit or cancel your changes and close Preferences without having to switch back to it, as well as a button to bring it back to the front without having to find it via alt-tab or the taskbar.
- Page list right-click menu includes *Expand All* and *Collapse All* options.
- *Command:* Added `Prefs COLLAPSEALL` lets you open the Preferences dialog with all categories collapsed (rather than remembering their last state). Combine with `PAGE` to show a page and collapse all other categories.

------------------------------------------------------------------------

Next: [customize](/Manual/release_history/opus13_detailed/customize.md)
