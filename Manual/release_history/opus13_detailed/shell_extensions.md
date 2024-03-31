### Directory Opus 13 - Detailed release notes

# Shell Extensions

- (Configured via Preferences / Miscellaneous / Shell Extensions.)
- Categorised, searchable list of all shell extensions installed on your machine.
- Shell extensions can be blocked via UI. Replaces old Advanced settings (ignore_context_menus/allow_context_menus).
- All extension types can now be blocked, not just context menus.
- Lets you see any installed extensions which are blocked by default, allowing you to unblock them.
- Lets you see any extensions which were automatically blocked due to a previous crash.
- Similar to NirSoft's ShellExView tool, but built-in and only affects Opus. ShellExView, AutoRuns, or similar should still be used for system-wide blocks.
- Menu (top-right "hamburger" icon) has several options for tech support:
  - Block a specific shell extension by ID, without having to find it in the list.
  - Save a file listing all shell extensions on the machine.
  - Import or export a list of blocked shell extensions. (Doesn't include ones blocked by default.)
- Option to run context menu extensions in a separate process (when possible). Helps isolate Opus from bugs in unstable third-party code.
- Option to hide Windows and third-party menu items has moved here.

------------------------------------------------------------------------

Next: [Miscellaneous Features](/Manual/release_history/opus13_detailed/misc_features.md)
