# Preferences

The Preferences dialog is the main interface for configuring Directory Opus. Almost all the options that control how Opus looks and behaves can be found in here.

![prefs_intro.png](/Manual/images/media/13/prefs_intro.png)

The first time you go into Preferences a short tutorial will step you through the key elements of the dialog.

##### Searching Preferences

The *Search* field at the bottom-left of the dialog can be used to filter Preferences for those pages and options that match what you type. To use the search filter, click on it (or press **F3**) and start typing.

In the screen shot below, we searched for *colors*:

![prefs_search.png](/Manual/images/media/13/prefs_search.png)

Any pages and items on those pages that match the search term are highlighted.

To clear the filter and display all pages again, click the little **X** button at the right of the search field, or activate the field and press the **Escape** key.

##### Apply vs Save

Most pages in Preferences require you to click **OK** or **Apply**, in the bottom right, before their changes take effect.

A few pages are different, where changes on them take effect immediately. These tend to be pages which modify cosmetic options, such as Colors and Fonts. When on those pages, there will be a **Save** button instead of an **Apply** button.

You can identify those pages by the ![prefs_autoapply.png](/Manual/images/media/13/prefs_autoapply.png) symbol at the top-right of the window.

Whichever type of page you are on, you can always click **Cancel** to revert any changes you have made since you last clicked **Apply** or **Save**. The *Preferences Menu*, discussed below, also give you more granular choices for reverting changes to some or all Preferences pages.

##### Favorite Pages

Pages you use a lot can be favorited, which puts a gold star next to them and adds a shortcut to them in the special *Starred* category at the top of the list.

A page's favorite status can be toggled by clicking the star next to its name when the mouse is over it, or via the context menu when you right-click a page in the list.

##### Preferences Menu

At the very top-right of the Preferences dialog is the ![prefs_menu.png](/Manual/images/media/13/prefs_menu.png) button, which opens the menu. This contains a number of useful commands:

- **Help**: Opens this manual.
- **Preferences introduction**: Re-plays the tutorial about the Preferences window.
- **Copy page shortcut**: Places a command string in the clipboard which, if used in a toolbar button, menu item or hotkey, will open the current Preferences page. For example, \`Prefs PAGE="colors"\` is the command to open the *Display / Colors and Fonts* page.
- **Revert changes**: Restores some or all Preferences settings to their values when Preferences was opened. This even works if you have clicked the **Apply** button. You can undo changes at any time as long as you don't close the Preferences window.
  - **Revert visible**: (Only available for certain pages.) Reverts only the currently displayed settings. For example, if you are looking at *Colors and Fonts* and the *File display background* colors are selected, only those will be reverted, with other colors left alone.
  - **Revert page**: Reverts changes made to the current Preferences page. For example, if you are looking at *Colors and Fonts*, all settings within that page will be affected.
  - **Revert ALL**: Reverts all Preferences settings on all pages.
- **Factory reset**: Resets some or all Preferences settings to their default values.
  - **Factory reset visible**: (Only available for certain pages.) Factory resets only the currently displayed settings.
  - **Factory reset page**: Factory resets the current Preferences page.
  - **Factory reset ALL**: Factory resets all Preferences settings on all pages. (Note that [Backup and Restore](/Manual/preferences/backing_up_and_restoring_preferences.md) provides a full configuration reset option, if you also want to reset things like toolbars and hotkeys which live outside of Preferences.)
- **Reset dialog font**: Use this if you have accidentally chosen a dialog font that makes the window too large to work with.
- **Change configuration mode**: Lets you change between the two different configuration modes that Opus supports.
  - **Private configuration**: Each user of the computer will have their own Opus configuration, completely separate from every other user's.
  - **Shared configuration**: There is only one global Opus configuration, and all computer users share it (so changes one user makes to the configuration affects all other users).
- **Backup & Restore**: Access the Preferences [Backup and Restore](/Manual/preferences/backing_up_and_restoring_preferences.md) system.

##### Page List Context Menu

Right-click the page list for a small menu of options:

- **Expand all**: Expands all categories in the list.
- **Collapse all**: Collapses all categories in the list. (If the list has keyboard focus, pushing the minus key is similar.)

If a page is right-clicked, these items are also included:

- **Favorite page**: Similar to clicking the favorite star on the left of the page name (see *Favorite Pages*, above).
- **Copy page shortcut**: As in ![prefs_menu.png](/Manual/images/media/13/prefs_menu.png) menu, puts a command to open the page into the clipboard.
- **Revert page**: As in ![prefs_menu.png](/Manual/images/media/13/prefs_menu.png) menu, reverts changes made to the page since Preferences was opened.
- **Factory reset page**: As in ![prefs_menu.png](/Manual/images/media/13/prefs_menu.png) menu, resets the page to its default values.
