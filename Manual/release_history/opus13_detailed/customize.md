##### Directory Opus 13 - Detailed release notes

# Customize

- General:
  - Customize and button editors are no longer always on top of other windows (e.g. the manual).
  - While editing toolbars, Lister and viewer windows have titlebar buttons to commit or cancel your edits and exit Customize mode, without having to switch to the Customize dialog. A third button takes you to the Customize dialog without having to find it via alt-tab or the taskbar.
- Toolbars tab:
  - Improved the way per-toolbar background images, colors and fonts work, with regard to overriding the main Preferences settings.
  - Right-clicking a toolbar in the list provides alternative ways to factory-reset a toolbar or undo unsaved changes to it.
- Context Menus tab:
  - Right-clicking a context menu in the list provides a new "Edit Alongside Default" option. This opens your copy of the menu beside the default version, allowing you to compare the two and drag defaults back to your menu.
  - Similar to the Toolbars tab, right-clicking a context menu in the list provides reset and undo options.
- Keys tab:
  - There are now two search fields: one that finds the key(s) you push; another that finds the command or name you type. (Previously, there was only one search field, with a button to toggle mode.)
  - Hotkey list now lets you select a category to filter it, instead of showing one long list.
  - New "Conflicts" category shows all conflicting keys (where two commands are assigned to the same key and need fixing).
  - New "Quick Keys" category, displays keys assigned to Find-As-You-Type and the Filter Bar.
  - Categories that contain standalone hotkeys (one not defined in toolbars or elsewhere) can be reset to defaults via their context menus.
  - "Quick Keys" and "Favorites" category context menus have options to jump to their respective Preferences pages and edit them.
  - When a command has multiple hotkeys assigned, individual keys can now be disabled rather than all-or-nothing.
  - Lister hotkeys can now be set to only apply when the folder tree has focus.
  - Whether a standalone hotkey is system-wide is now defined at creation, and can't be changed later (other than deleting and recreating it).
  - Hotkeys can turn on "Allow additional qualifiers" to make them less strict.
    - For example, a Shift+X hotkey won't normally trigger if <kbd>Ctrl</kbd> is also held down, but will with the new option.
    - Commands in hotkeys can test if extra keys are held down.
    - This lets you assign a command `Go UP USEQUALKEYS` to a single hotkey, such as Backspace. Shift+Backspace, Ctrl+Backspace and Alt+Backspace will also launch it, and the function will be able to see which qualifiers were held down when it was launched.
    - The same applies to functions that use `@keydown` to test which keys are held down.
  - Normally, commands do not see a hotkey's explicitly specified keys as being down:
    - That would make it impossible to run some commands (intended for toolbars) on some keys, since the keys would change what the commands do.
    - Since those keys must be down for the hotkey to trigger at all, conditional logic based on them usually doesn't make sense.
    - When a hotkey turns on "Allow additional qualifiers", this changes: Commands it runs can test for all qualifier keys.
- Commands tab:
  - Now provides a comprehensive list of pre-made buttons you can drag to toolbars and menus, without editing any code.
  - Includes all commands that are part of the default configuration, plus a few extras. Automatically kept up to date when we make changes to the defaults.
  - Commands can be filtered by category, and you can find things by typing into the search field.
- User Commands tab:
  - User Commands are now managed in their own tab, instead of hidden in the Commands tab.
- Default Toolbars tab:
  - New tab which displays the built-in, default toolbars. Now you can look at the defaults without resetting the toolbars you're actually using.
  - Commands (or entire menus) can be dragged to your toolbars. A convenient way to restore things you removed but later need again.
  - Can highlight commands based on the Opus version that added them. Use this to update custom toolbars with new functionality.
  - Of course, you can still reset your real toolbars to get the latest defaults and revert any changes you've made.
- Button editor:
  - "Run with logging" (<kbd>Shift+F5</kbd>) mode for testing buttons. When on, a log displays each line as it runs, including all substitutions for `{...}` codes. Useful for debugging complex buttons and conditional lines.
  - Suggestion popups that complete command, argument and modifier names as you type. Push Ctrl+Space to make suggestions appear after moving the cursor.
  - Arguments menu now marks arguments used on the current line. Helps when you need to find an existing argument to add parameters to it.
  - Long argument (etc.) menus now have scrollbars instead of going multi-column.
  - New button editor layout, and removed the cut-down "Simple" mode, since it didn't really simplify things.
  - New "Show hotkey in label" option, for buttons inside menus. Automatically displays the button's hotkey, if any, on the right of the menu, without having to manually duplicate it in the label string. Has no effect on buttons that aren't inside menus.
- Clipboard in customize mode:
  - Right-clicking a combined menu-button now gives options to copy just the button part, or the whole button-and-menu, to the clipboard.
  - Right-clicking a menu, when a button is in the clipboard, now gives options to paste the button into the menu, as well as alongside it.
  - Right-clicking a menu-button, with a button in the clipboard, gives the additional option of pasting over just the button part.
  - In Customize mode, the context menu you get when right-clicking empty space on a toolbar (or a menu-editor's titlebar) now includes the option to undo unsaved changes. (Also includes the factory reset option, which isn't new there.)

------------------------------------------------------------------------

Next: [Default Toolbars & Menus](/Manual/release_history/opus13_detailed/default_toolbars.md)
