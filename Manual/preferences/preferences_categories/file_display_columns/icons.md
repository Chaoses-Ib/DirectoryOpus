# Icons

Contains options relating to how icons appear.

- **Show shortcut arrows and other icon overlays**: If this option is off, Opus will not display icon overlays such as arrows in the corners of shortcut icons, shared folder indicators, or status indicators from source-control and folder-syncing shell extensions (e.g. TortoiseSVN and DropBox).
- **Show generic icons**: Most file types use the same icon for all files of that type - for example, all .txt files generally have the same icon. However some file types (most notably **.exe** files) can have a different icon for individual files. Loading this icon can slightly slow down the display time of folders, particularly on network drives, so you can use this option to control whether Opus displays generic icons rather than per-file icons for these types of files.

##### Status icons for icon overlays

Windows only allows a maximum of 15 icon overlays in the system, which makes them unreliable - as soon as you have a few programs installed which use overlays, they have to fight it out and the winner is often completely random. Opus lets you divert *some* icon overlays to its own **Status** column, which provides a more reliable indicator for these specific types of overlay.

- **Show cloud storage icons in the Status column**: When inside a cloud storage folder (e.g. OneDrive or Dropbox), this will cause an icon representing the file's synchronization state to be shown in the Status column automatically. Similar status icons will also appear next to files in display modes like List and Thumbnails.
- **Show TortoiseSVN icons in the Status column**: For developers using the free TortoiseSVN source code control utility, Opus can optionally display a file’s SVN status as an icon in the Status column. Other than the status icon appearing larger and more distinctive than the usual icon overlay that Tortoise uses, another advantage is that as Tortoise normally uses 8 or icon overlays for itself, it can crowd out other shell extensions. Using this option in Opus gets around the limit as the status is taken directly from Tortoise rather than via the icon overlay.
- **Tortoise icon set**: Lets you select the icon set to use when showing Tortoise status.
- **Disable Tortoise icon overlays in the file display**: This lets you disable the Tortoise icon overlay handler completely (so that the Status column is the only place the TortoiseSVN status icons will appear). Note that this feature requires TortoiseSVN version 1.9.3 or greater. Turning this on will free up the icon overlay slots for other applications (though within Opus, not within Explorer).
