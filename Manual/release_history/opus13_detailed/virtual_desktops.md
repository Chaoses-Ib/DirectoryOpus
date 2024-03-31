### Directory Opus 13 - Detailed release notes

# Virtual Desktops

- Replaced the singular "isolate virtual desktop" option with more granular control:
  - Preferences / Layouts and Styles / Default Lister / Always open Default Lister on the current desktop
  - Preferences / Layouts and Styles / Default Lister / Avoid switching desktops to find existing Listers
  - Preferences / Viewer / Standalone Viewer / Avoid switching desktops to find existing viewers
- Layouts can remember and restore windows across one or more virtual desktops, or just the current one.
- Layouts set to close other windows can be configured to only close those on the current desktop, or those on all desktops. Similar options exist for the various methods of opening new windows under Preferences / Launching Opus.
- If Opus is set to remember open windows across restarts, it can be told to restore them to their original virtual desktops.
- Commands:
  - `Prefs LAYOUTCLOSELISTERS=...` -- Takes new "current" and "all" parameters to override the main setting. E.g. Prefs LAYOUTCLOSELISTERS=yes,current
  - `Prefs LAYOUTNOVIRTDESKTOP` -- Can override the virtual desktop setting when loading a layout.
  - `Show USEEXISTING=...` -- Replaces the old NOUSEEXISTING (which is hidden but still works) and allows you to specify "avoid" and "noavoid" keywords to override the "Avoid switching desktops" option with specific buttons, or when a key is held down, and so on.
  - `DOpusRT.exe /cmd:active,thisdesktop` -- Looks for the active Lister, but only on the current virtual desktop.
- Scripting:
  - Lister and Viewer objects have "desktop" properties which return their desktop's ID.
  - Lister and VIewer objects have IsOnCurrentDesktop and MoveToDesktop methods.
  - A new DOpus.GetListers method, similar to the existing "listers" property, but passing the "c" flag filters out windows not on the current desktop.

------------------------------------------------------------------------

Next: [Shell Extensions](/Manual/release_history/opus13_detailed/shell_extensions.md)
