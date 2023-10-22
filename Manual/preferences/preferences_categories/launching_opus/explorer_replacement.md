# Explorer Replacement

This page lets you configure the [Explorer Replacement](/Manual/basic_concepts/explorer_replacement.md) system, which controls if and when Opus will replace Explorer when new folder windows are opened.

- **Don't replace Explorer**: Explorer Replacement mode is disabled. You can still access Opus in many ways, but it will not open in place of Explorer.
- **Replace Explorer for all file system folders**: Opus will replace Explorer for file-system folders, but not for virtual folders. For example, if you had a shortcut to *C:\Files* on your desktop and double-clicked it, Opus would open - but double-clicking the *Recycle Bin* on the desktop would continue to open Explorer.
- **Replace Explorer for all folders**: Opus will replace Explorer for all folders (see note below).
- **Replace Explorer for all but the following folders**: Opus will replace Explorer for all folders except those you add to the list below.

![](/Manual/images/media/explorer_replacement.png)

Use the toolbar buttons to add folder to (![](/Manual/images/media/favorites_-_add.png)) or remove (![](/Manual/images/media/favorites_-_delete.png)) folders from this list. Any folders listed here will continue to open in Explorer when launched in a new window; all others will open in Opus.

- **Open external folders in a new tab**: When Opus intercepts an action that would normally open Explorer, it opens a new Lister instead. If this option is turned on and you already have a Lister open, the folder is opened in a new tab in the existing Lister instead of in a new Lister. The option also affects what happens when archives are opened from outside of Opus, if Opus is set as the system default handler on the [Zip Files](../zip_and_other_archives/zip_file_options.md) page. (If you are using the virtual desktops feature of Windows 10 and above, Opus will normally only look for existing windows on the active virtual desktop. You can change this via the advanced **[Advanced](../miscellaneous/advanced_options.md)** setting.)
- **Open all Default Lister tabs when opening a new window**: This option controls what Opus does when it intercepts an action which would open a new folder tab but there is no existing window for the tab to open in. If the option is off, Opus will open a window which only displays the folder in question. If the option is on, Opus will open your Default Lister, including any initial folders and folder tabs, and then open an additional tab for the folder in question.

The Explorer Replacement options only affect what happens when some action causes a new folder window to be opened. For example, double-clicking a folder on the desktop, pressing **Windows+E**, or performing an action within a third-party program that would normally cause an Explorer window to open - in these sorts of cases, Explorer Replacement mode will cause an Opus Lister to open instead of an Explorer window.

Opus does not replace the system file open or save dialogs, so these options have no effect on those functions.

In Vista and Windows 7, Opus will not open the *Control Panel* even if **Replace Explorer for all folders** is turned on - the Control Panel (and its various sub-pages) will always open in Explorer.
