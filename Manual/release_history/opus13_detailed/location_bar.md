### Directory Opus 13 - Detailed release notes

# Location Bar

- General:
  - Preferences / Location Bar.
  - "Location Bar" is the new name for the "File Display Border" and toolbars within it. This is the area directly above each file display, usually containing a path field and buttons for navigation.
  - The option to ignore clicks on the destination Location Bar now only applies to left clicks. Other clicks (e.g. to open context menus or run RMB/MMB actions) now take place immediately, and don't make that side source (unless the action they perform does so inherently).
  - If the Location Bar's icon is turned on, clicking it now makes that side the source.
  - Buttons on Location Bar toolbars can now override their text and background colors.
  - Thumbnail Size sliders on Location Bar toolbars now only affect the side they are attached to, by default. They can be given arguments to override this.
- Path Fields:
  - Path field appearance and behavior is now configurable via the Preferences UI. (The old path field "args" string no longer needs to be edited manually, unless you want to override something for just one particular field.)
  - You now set a maximum width for path fields breadcrumbs (path components).
  - New option to display only labels (no letters) for drives in path field breadcrumbs.
  - When in a directory below Desktop, the path field now shows "Desktop \> Folder Name" instead of just "Folder Name".
  - Added option to show or hide the "Network" breadcrumb at the start of UNC paths. (Previously, whether or not this was there depended on how you navigated to the path. It is now always added or removed according to your choice.)
- Home Button:
  - (Configured via Preferences / Frequently Used Paths / Home Directory, or right-click the button.)
  - The default toolbar now includes a Home button, similar to the one in web browsers.
  - Initially, the Home button goes to the first folder which the current tab opened (like the `Go INITIALDIR` command).
  - You can make the button go to a different folder via its right-click context menu, or through Preferences.
  - (Of course, you can add buttons for as many folders as you want there, or anywhere else on your toolbars. The Home button makes things easier for people who don't know how to do that.)
  - You can drop files on the button to sent them to your Home folder, and middle-click it to open the Home folder in a new tab.
- Commands:
  - `Go HOMEDIR` is the same as clicking the Home button.
  - `Go HOMEDIR=update` configures the Home button to go to the current folder from then on. Similar to editing it via Preferences or the button's context menu.
  - `Go HOMEDIR=reset` reverts the Home button to going to the current tab's initial folder. Also available in the button's context menu.

------------------------------------------------------------------------

Next: [Filter Bar](/Manual/release_history/opus13_detailed/filter_bar.md)
