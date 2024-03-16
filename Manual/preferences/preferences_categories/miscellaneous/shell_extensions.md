# Shell Extensions

This page shows a list of all the various shell extensions you have installed, and lets you block them *from within Opus*. It performs a similar function to the NirSoft [ShellExView](https://www.nirsoft.net/utils/shexview.html) tool, except that tool blocks shell extensions globally.

Shell extensions implement things like context menus and information columns. If you find one that causes problems with Opus, you can use this page to disable it and see if the problem is resolved.

The category list on the left shows all the various categories of shell extension. *Context Menu* is probably the most used category - and on Windows 10 and 11, *Context Menu UWP* implements the "new style" of context menu item.

You can use the search field at the top to search extensions by name. To block an extension, select it in the list and click the **Block** button. Blocked extensions show a "no" icon in the list, and can also be found listed in the *Blocked* category. You can unblock an extension in the same way.

Right-click an extension to block or unblock it, and to get more information about it by searching for it on Google.

The ![](/Manual/images/media/13/prefs_menu.png) page menu in the top-right corner of the page has commands to block items manually, and to import and export your block list if you want to move it to another system.

##### Other options

At the bottom of the page are two related options:

- **Access context menus out-of-process if possible**: Over the years we've found that context menus are the shell extensions that tend to cause the most problems, so in Opus 13 we've tried to improve this situation by moving them into a separate process if possible. That way, if a shell extension crashes or corrupts memory, Opus itself won't be affected. If you find this causes problems of its own you can turn it off here.
- **Hide Windows items on file context menus (shift overrides)**: If this option is on then any context menu items that come from the system (i.e. most of them) will be hidden by default when you right-click on a file or folder in Opus. The only items that will be displayed are those defined through Opus itself (e.g. *Cut*, *Copy*, *Paste*, *Delete*, *Rename*, *Properties*). This option is useful if you want to tidy up your context menus (as most context menus are generally quite messy once you have a lot of third-party software installed). Using Opus it's possible to hide all Windows items by default and then selectively add them back wherever you want (including on a sub-menu). Please see the [tip on the Resource Centre](https://resource.dopus.com/t/tip-organise-and-speed-up-context-menus/1204) for more information about doing that. If this option is on, you can force the display of the full context menu by holding the <kbd>Shift</kbd> key down when right-clicking the item.
