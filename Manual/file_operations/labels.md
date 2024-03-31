# Labels and Status Icons

The **Labels** system lets you assign your own labels to files and folders. A label has a name, and can define colors and font styles that modify the appearance of labeled files. Labels can also be used to override the default icon image for a file or folder, or define a status icon that can be shown in a separate column to flag important files. They can also cause a file or folder to become "pinned" to the top of the file list.

By default Opus defines five labels - *Blue*, *Green*, *Orange*, *Purple* and *Red*, and four status icons - *Checked*, *Flagged*, *Important* and *Pinned*.  You can use these labels (what you interpret them to mean is up to you) or define your own. For example, you could define a label called *Really Important* that displays files in red italics.

![](/Manual/images/media/13/labels_2.png)

Labels are defined through the [Label Definitions](/Manual/preferences/preferences_categories/labels/label_definitions.md) page in Preferences.

### Assigning labels

You can apply labels to files and folders on an ad-hoc basis, using the **Properties** drop-down menu on the default toolbar. The *Set Label* and *Set Status* sub-menus display a list of your defined labels and status icons, and lets you apply them automatically to selected files and folders.

![](/Manual/images/media/13/labels_status.png)

To label a file, select it, and then choose the appropriate label from this drop-down. Depending on the label definition, the file will change color instantly to match the assigned label.

Note that the options in the Status category are all still labels - they've simply been grouped under "Status" because all they do is define status icons. You can change this and create your own groups if you want.

### Stacked labels

More than one label may apply to a single file, and labels can “stack” on top of each other. For example, one label could turn all JPEG filenames green, while another might use bold for images which are at least 1920x1080 pixels. A 1920x1080 JPEG file would then have a bold green name. Each label definition has a “stop on match” flag which lets you prevent further combinations - once a label with “stop on match” is encountered, no further labels will be processed for that file.

### Wildcard labels

The [Label Assignments](/Manual/preferences/preferences_categories/labels/label_assignments/README.md) page in Preferences lets you apply labels to files and folders using wildcard patterns. For example, you could cause all Word documents to be labeled *Green* by creating a wildcard label assignment for **\*.doc** files. Labels can also use [filters](filtered_operations/README.md) to perform tests based on attributes other than file name or path.

By default explicitly applied labels override wildcard labels, but the Preferences setting *Favorites and Recent / Labels / Apply wildcard and label filters to explicitly labeled files and folder* lets wildcard labels stack on top of explicitly-assigned ones.

### Overriding file icons

In the image below, you can see an example of a label filter that is used to override icons for particular files. A label has been created (called **HD Image**) that defines a custom icon. A label filter has also been created that matches JPG files (it could be used to match more filetypes if desired) with a height of at least 1080 pixels. You can see in the Lister image at the bottom that the high resolution images are displayed with the custom icon, whereas the smaller images have the standard JPG icon.

![](/Manual/images/media/13/custom_icons.png) 

### Label storage

There are two ways that Opus can store labels that are assigned to a specific file or folder (as opposed to a wildcard or filter-based label). 

- On an NTFS-formatted drive (which is the most common type of file system these days) the label information is stored in an alternate data stream with the actual file itself. The advantage of this is that when you copy, move or rename the file, the label goes with it (if enabled on the [Copying Files / Attributes](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.md) page in Preferences).
- On other file systems, or if the option to store labels in the file system is turned off (on the [Labels / Options](/Manual/preferences/preferences_categories/labels/options.md) page in Preferences), Opus stores a list of the full filename and path of labeled files. That means that if you move a labeled file, the label will not go with it. You can view a list of all files labeled in this way from the **Label Assignments** page in Preferences, and use the controls there to clean up the labeled file list.

### TortoiseSVN support

For developers using the free TortoiseSVN source code control utility, Opus can optionally display a file’s SVN status as an icon in the *Status* column. This is controlled by the **Show TortoiseSVN icons in the Status column** option on the [File Display Columns / Icons](/Manual/preferences/preferences_categories/file_display_columns/icons.md) page in Preferences. If turned on, Opus will automatically add the appropriate SVN status icon to any other label icons displayed in the *Status* column.

Other than the status icon appearing larger and more distinctive than the usual icon overlay that Tortoise uses, this can help with the problem of limited icon overlays. Windows only allows a maximum of 15 icon overlays in the system, and Tortoise normally uses 8 or more of these for itself, crowding out other shell extensions. Using this option in Opus gets around the limit as the status is taken directly from Tortoise rather than via the icon overlay.

Note that this feature requires TortoiseSVN version 1.9.3 or greater.
