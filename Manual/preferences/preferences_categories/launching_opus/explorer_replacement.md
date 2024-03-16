# Explorer Replacement

This page lets you configure the [Explorer Replacement](/Manual/basic_concepts/explorer_replacement.md) system, which controls if and when Opus will replace Explorer when an action occurs that would normally open a new Explorer window.

Opus does not replace the system file open or save dialogs, so these options have no effect on those functions. Also, on Windows 10 and above what happens when you press <kbd>Win+E</kbd> is configured on a [separate page](launching_opus_from_the_win-e_hotkey.md).

- **Don't replace Explorer**: Explorer Replacement mode is disabled. You can still access Opus in many ways, but it will not open in place of Explorer.
- **Replace Explorer for all file system folders**: Opus will replace Explorer for file-system folders, but not for virtual folders. For example, if you had a shortcut to *C:\Files* on your desktop and double-clicked it, Opus would open - but double-clicking the *Recycle Bin* on the desktop would continue to open Explorer.
- **Replace Explorer for all folders**: Opus will replace Explorer for all folders (see note below).
- **Replace Explorer for all but the following folders**: Opus will replace Explorer for all folders except those you add to the list below.
- **Open a new tab instead of a new window**: Open a new tab when intercepting an action that would normally open Explorer, rather than a new Lister.
- **Open all Default Lister tabs when opening a new window**: When a new window opens due to Explorer Replacement, your entire Default Lister, including any initial folders and folder tabs, will be opened first - and then an additional tab will open for the folder in question.
