# Label Definitions

This page lets you create and edit *[Labels](/Manual/file_operations/labels.md) -* combinations of colors and font styles that you can apply to files and folders. Any file or folder can be assigned a label, and you can use wildcards or [filters](/Manual/file_operations/copying_moving_and_deleting_files/filtered_operations/RAEDME.md) to automatically label based on filename (so, for example, you could automatically label all your .doc files).

![](/Manual/images/media/labels_1.png) 

For each label, you can specify text and background colors for when the item is both selected and unselected. In the above screen shot you can see that the *Blue* label specifies that items assigned this label will display blue text when not selected. No other text colors have been defined (this is indicated by the checkerboard pattern) and so the normal colors for the items will be used for its background color, as well as the color when selected.

The *selected* text and background colors defined here will not be used if items are displayed using visual styles, unless **Visual styles override file selection colors** is turned off in [Display Options](../display/display_options.md).

A label can also specify a color that is applied to labeled items' icons. This color is applied algorithmically to the existing icon - it doesn't make Opus show a different icon for the items - so your results may vary as to how effective this is. For most icons however it works fine:

![](/Manual/images/media/labels_2.png) 

A label can also be used to specify custom icons that are used for the labeled files or folders. To specify a custom icon for a label, click the **Browse** button. You can use icon files (*.ico*, *.icl*), icons from programs (*.exe*, *.dll*) or any image file format that Opus supports. If you specify an image Opus will automatically scale and convert it to icon format. Labels can also define a status icon that can be shown in a separate column to flag important files.

You can use the **Category** field to arrange your labels in categories - the list of labels shown in the **Properties** drop-down menu on the default Lister toolbar will be sorted into categories by default.

There are two ways that Opus can store labels that are assigned to a specific file or folder (as opposed to a wildcard or filter-based label).

- On an NTFS-formatted drive (which is the most common type of file system these days) the label information is stored in an alternate data stream with the actual file itself. The advantage of this is that when you copy, move or rename the file, the label goes with it (if enabled on the **[File Operations / Copy Attributes](../file_operations/copy_attributes.md)** page in Preferences).
- On other file systems, or if the option to store labels in the file system is turned off, Opus stores a list of the full filename and path of labeled files. That means that if you move a labeled file, the label will not go with it. If the **Enable label storage in the file system** option is turned on, Opus will look for labels stored in the file system. Turn on the **Automatically store labels in the file system** option to store labels like that by default. If the first option is turned on but the second one is off, you can still store a label in the file system using the arguments to the **[Properties](/Manual/reference/command_reference/internal_commands/properties.md)** command.

By default explicitly applied labels override wildcard labels, but the **Apply wildcard and label filters to explicitly labeled files and folders **option lets wildcard labels stack on top of explicitly-assigned ones.
