##### Directory Opus 13 - Detailed release notes

# File Copying

- Copy via Shell API:
  - Where possible, Opus now defaults to copying via the very-high-level API provided by the Windows Shell, as used in File Explorer.
  - Faster copying with some devices and networks.
  - Enables remote file copying (also known as "copy offload" or "server-side copy"):
    - When copying between two shares on the same server, the server can do the work itself.
    - File data doesn't need to come over the network to your computer and then back to the server. Copying is as fast as the server's drives, without the network bottleneck.
    - Automatic, when supported by the server. Nothing to configure at either end with Windows servers. Support with other NAS devices varies and is down to the manufacturers.
  - User interface, progress/error/replace dialogs, copy queues, etc. are still handled by Opus, with no loss of functionality, regardless of copy method or remote file copying.
  - Opus automatically falls back on its own copy method for situations where the API cannot be used (e.g. archives and FTP sites).
  - Can be turned off via **Preferences / Miscellaneous / Advanced: \[Filesystem\] copy_allow_delegation**, if you find the new mode slower for your devices.
  - *Command:* \`Copy DELEGATE\` -- Allows overriding the global setting for individual copies.

- Progress dialog:
  - More accurate speed and time estimates.
  - Average, peak and current speeds are shown on the graph, reducing clutter in the rest of the dialog.
  - Speed graph now antialiased and drawn using Direct2D.
  - Speed graph colors configurable in Preferences.
  - Option to retain speed information from one queued job to the next (if using the same drives).
  - Errors list (for unattended mode) now a tab rather than a separate window.
  - Option for faster calculation of file counts and sizes using Everything. (See [Everything](everything.md) section.)
  - Progress indicators on the Jobs Bar have tooltips if their text is truncated.

- In-progress files:
  - "Ghost" files can appear in destination folders to represent files which are yet to be copied.
  - These appear faded and cannot be opened or modified, since they do not really exist yet. Once the real destination file is created, it appears normally and replaces its placeholder.
  - Icon overlays indicate source files that are part of an active copy and the destination file currently being written. (In addition to the older overlay indicating queued files.)
  - Options under Preferences / File Operations / Copying Files can turn all of this off.

- Copy queues:
  - Copy queue now a tab in the Progress dialog, rather than at the bottom.
  - "Switch to Queue tab when new jobs are queued" option controls if the tab is activated when it appears, or stays in the background.
  - Larger buttons for managing the queue. Appear on mouseover.
  - You can use drag & drop to reorder queued jobs, or drag them to another queue.
  - When a copy is paused, you can drag the progress dialog's window icon to another progress dialog to enqueue it.
  - Automatic copy queue rules have changed slightly:
    - Copies into the same archive are now assigned to the same queue. This rule takes priority over all others.
    - Previously, the source folder was more important than the destination for some folder types; priority is now always given to the destination.
    - Copies to network shares now queue behind other copies to the same share. (Previously, both source and destination had to be the same for them to queue.)

- Copy naming:
  - New option, "Automatically rename when copying virtual files". If on, when you drag from a web browser to Opus, and the same name already exists, the new file will be renamed automatically without prompting.
  - New option to change the "Copy of" naming template used when duplicating a file in-place.
  - New option to change or remove the "- Shortcut" suffix when creating shortcuts. (Note that Opus no longer respects the system-wide registry setting that could only enable or disable the suffix.)
  - New option, "Show rename presets in replace dialog". Adds some or all rename presets as menu choices when prompted to replace or rename due to a name conflict.

- File permissions:
  - New option, "Update permissions even if it would trigger a UAC prompt". Turn off to avoid a UAC prompt if a file could be moved without elevation but its permissions could not be updated.
  - New options which modify the way "Update permissions/encryption to match destination when moving on same drive" works. The defaults match the old behavior in Opus 12:
    - Change ownership to match destination (off by default): Changes ownership of the file to match that of the target folder. This can prevent unwanted permissions being granted to the old owner due to target folders which grant access to CREATOR OWNER.
    - Preserve explicit (non-inherited) permissions (on by default): When on, explicit, non-inherited permissions on the old file are carried over after it is moved, and merged with permissions inherited from the new parent folder; only old inherited permissions are removed. When off, all old permissions are removed and replaced by those inherited from the new parent folder.

- Flat View and expandable folders:
  - New option, "Copy to single level if all items are in the same folder".
  - Allows simple copying out of sub-folders, without recreating the parent hierarchy or being prompted, if the selection is all in the same place.
  - Still lets you recreate the hierarchy when multiple sub-folders are involved.
  - (See [File Display](file_display.md) for details on the new *expandable folders*.)

- Multi-Window Source and Destination:
  - By default, the *Source and Destination* concept now only applies between the two sides of a dual-display window, and not between top-level single-display windows.
  - New option, "Single display Listers have source/destination modes", can restore the old behavior.
  - People tended to find this concept confusing, or simply didn't use it, so it's now off by default.
  - Explicit actions between windows still always work as before (e.g. drag & drop or copy & paste). This only affects what happens if you select files in one single-display window and click *Copy Files* or *Move* to send them to another.

- Commands:
  - \`Copy UPDATEEXISTING\` -- Now allows "smaller" and "larger" tests for file size (rather than just different).
  - \`Copy UPDATEALL\` -- Now allows the same tests as \`Copy UPDATEEXISTING\`.
  - \`Copy COPYFILETIMES\` and \`Copy COPYDIRTIMES\` can now take "all", "none", "onlymodified" or "onlycreated" keywords to override the main Preferences options.
  - Old \`Copy COPYCREATIONTIME\` is deprecated and hidden from argument lists, but still works for compatibility.
  - \`Copy FLATVIEWCOPY=autosingle\` -- Combined with "ask" or "recreate", allows command to do the same as "Copy to single level if all items are in the same folder".
  - \`Clipboard PASTE COPYCOMMANDARGS ...\` -- Provides additional arguments to the Copy command if that's what Clipboard PASTE ends up running.
  - \`Set PROGRESSCMD=...\` -- Can create hotkeys to sends commands to all current progress dialogs. Commands are "minimize", "restore", "show", "pause", "resume" and "abort".

------------------------------------------------------------------------

Next: [everything](/Manual/release_history/opus13_detailed/everything.md)
