# Label Definitions

This page lets you create and edit [labels](/Manual/file_operations/labels.md) - combinations of colors and font styles that you can apply to files and folders. Any file or folder can be assigned a label, and you can use wildcards or [filters](/Manual/file_operations/filtered_operations/README.md) to automatically label based on filename (so, for example, you could automatically label all your .doc files).

- **Label**: Specify the name for the label. This will be shown in the *Label* column for any files it's assigned to, and also used in generated label lists in toolbars and menus (e.g. the **Properties** dropdown menu in the default toolbars).
- **Category**: You can arrange your labels in categories - the list on the left groups your labels into two categories by default (*Colors* and *Status*) but you can also add your own.
- **Bold**, **Italic**, **Underline**: Applies the checked styles to files with this label.
- **Unselected text**: Specify the unselected text and background colors for files with this label.
- **Selected text**: The selected text and background colors for files with this label.
- **Icon color**: Tints the file icon with the specified color.
- **File icon**: Override the file icon.
- **Status icon**: Adds a status icon for files with this label (shown in the *Status* column).
- **Show in Label column**: Prevents the label from being shown in the *Label* column.
- **Pin to top**: Files with this label will be sorted to the top of the list automatically (NTFS filesystems only).

Note tha the *selected* text and background colors defined by a label won't be used if items are displayed using visual styles, unless **Visual styles override file selection colors** is turned off on the [Color Blending](../colors_and_fonts/color_blending.md) page.
