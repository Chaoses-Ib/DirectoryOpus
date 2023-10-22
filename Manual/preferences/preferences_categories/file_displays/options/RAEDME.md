# Options

This page contains various options that let you adjust the behavior of File Displays.

- **Automatically select first file in folder**: When navigating to a new folder, this option causes the first item in the list to be selected automatically. This option does not apply to Power mode file displays - there is a separate option for them on the [Power Mode](../file_display_modes/power_mode/RAEDME.md) page.
- **Reset focus entry when sorting file list**: Turn this on if you don't want the file display to scroll when you change how it is sorted (e.g. by clicking a column header). With this option off, sorting causes the file display to scroll so the file which had focus before the change remains visible in its new position. With this option on, the file display does not scroll and instead gives focus to whichever file ends up in where the previous file with focus was.\<WRAP\>  
  If the file with focus had been scrolled out of view before the change, it will be ignored and focus will reset to the top visible item. As an example, if you scroll to the top of the file display, click the 5th item down, then sort by date: If the option is on, you will still be at the top of the file display, and focus will be on whatever is the new 5th item down. If the option is off, focus will be on the same file as before and the file display will scroll to ensure it is still visible.

\</WRAP\>

- **Show sort header in icon modes**: Normally column headers are only shown in details and Power mode. If you turn this option on, column headers will be shown in the icon modes (like thumbnails) too. Although there are no columns in those modes, you can still use the header as a convenient way to sort or group the file list.

##### Single display

- **Single display Listers have source/destinaiton modes**: When a Lister is in dual-display mode, one side is always the source and one side is always the destination. When a Lister is in single display mode, it's possible for one whole Lister to be the source and another one to be the destination. With this option turned off, single display Listers don't participate as source/destination. See [Source and Destination](/Manual/basic_concepts/source_and_destination.md) for more information.

##### Dual display

- **Set new panel to source when switching to dual file display**: When you switch a Lister into dual display mode, this option causes the newly opened file display to become the source, and the original file display the destination.
- **Specify initial folder when switching to dual file display**: Normally when you switch a Lister into dual display mode, the folder that was already open is opened in the second file display. This option lets you specify a specific folder that will be the default for the newly opened display (so you could, for instance, always have the second file display open to display the Desktop). The **Tab group** option lets you configure a tab group to be opened automatically when switching to dual display mode (instead of just a folder).
