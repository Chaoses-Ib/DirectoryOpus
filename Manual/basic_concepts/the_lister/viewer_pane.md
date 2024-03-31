# Viewer Pane

The Viewer Pane is an integrated image and document viewer that can be displayed within the Lister. When it is enabled, it will automatically show (if possible) the contents of the most recently selected file. It provides a very quick way to preview files - simply navigate to the folder in question, and click on the file to show it. Using the cursor keys you can easily move up and down a list of files, viewing them as you go.

![](/Manual/images/media/13/viewer_pane.png)

### Accessing the viewer pane

The easiest way to display the Viewer Pane in a Lister is with the ![](/Manual/images/media/13/menu_toolbar_-_viewer_pane.png) button on the default toolbar. You can also press <kbd>F7</kbd>, or select the **Viewer Pane** command from the **Lister** dropdown menu.

### Viewing a file

With the viewer pane displayed, viewing a file is as simple as selecting it in the file display. Opus can natively show many types of image files, and comes with [plugins](/Manual/preferences/preferences_categories/viewer/viewer_plugins.md) to display common document formats like Word and PDF files (providing suitable viewers are installed in the system). The title bar of the viewer pane displays the name of the currently viewed file, as well as some information about it - if it's an image format, it will generally display the resolution and type of image. For files that require the use of a plugin, the name of the plugin will generally be shown.

### Viewer pane title bar

![](/Manual/images/media/13/viewerpane_titlebar.png)

There are a number of buttons in the viewer pane's title bar:

- **Previous File**: Moves the selection in the file display to the previous file (and displays it in the viewer pane).
- **Next File**: Moves the selection to the next file.
- **Rotate Left**: Rotate the currently displayed image 90 degrees to the left. Note that this does not modify the image on disk - the rotation is not permanent, it simply affects the current display in the viewer pane. If you want to permanently rotate an image you can use the **[Image Conversion](/Manual/additional_functionality/image_conversion/README.md)** function.
- **Rotate Right**: Rotate the currently displayed image 90 degrees to the right.
- **Zoom In**: Zoom into (magnify) the currently displayed image. You can also zoom in by holding the <kbd>Ctrl</kbd> down and turning the mouse wheel.
- **Zoom Out**: Zoom out of the currently displayed image. You can also zoom out by holding the <kbd>Ctrl</kbd> key down and turning the mouse wheel.
- **Original Size**: Display the current image at its original (full) size.
- **Fit To Window**: Scale the image to fit to the size of the window. This setting only scales large images down to fit in the window - it does not scale images up that are smaller than the window.
- **Grow To Window**: Scale the image to match to the size of the window. By contrast with **Fit To Window**, this setting will scale a small image up to fill the window as well as scaling a large image down.
- **Toggle Layout**: This will toggle the layout of the viewer pane between vertical (displayed to the right of the Lister, as in the above screenshot) and horizontal (displayed at the bottom of the Lister).
- **Close**: Closes the viewer pane.

### Scrolling the viewer

Using the **mouse wheel** over the viewer pane will move images and documents up and down (where applicable, and assuming third party viewers don't use the wheel for something else). Holding the <kbd>Alt</kbd> key also allows you to scroll left and right with the mouse wheel with Opus's built-in image viewer and plugins that support it.

### Control bar

![](/Manual/images/media/13/viewerpane_controlbar.png)

As well as the buttons in the title bar, you can turn on the control bar at the bottom of the viewer. The **Show control bar** option is on the **[Viewer / Viewer Pane](/Manual/preferences/preferences_categories/viewer/viewer_pane.md)** page in Preferences.

The buttons in the control bar are:

- **Previous File**: Moves the selection in the file display to the previous file (and displays it in the viewer pane).
- **Next File**: Moves the selection to the next file.
- **Rotate Left**: Rotate the currently displayed image 90 degrees to the left. Note that this does not modify the image on disk - the rotation is not permanent, it simply affects the current display in the viewer pane. If you want to permanently rotate an image you can use the **[Image Conversion](/Manual/additional_functionality/image_conversion/README.md)** function.
- **Rotate Right**: Rotate the currently displayed image 90 degrees to the right.
- **Zoom In**: Zoom into (magnify) the currently displayed image. You can also zoom in by holding the <kbd>Ctrl</kbd> down and turning the mouse wheel.
- **Zoom Out**: Zoom out of the currently displayed image. You can also zoom out by holding the <kbd>Ctrl</kbd> key down and turning the mouse wheel.
- **Original Size**: Display the current image at its original (full) size.
- **Fit To Window**: Scale the image to fit to the size of the window. This setting only scales large images down to fit in the window - it does not scale images up that are smaller than the window.
- **Grow To Window**: Scale the image to match to the size of the window. By contrast with **Fit To Window**, this setting will scale a small image up to fill the window as well as scaling a large image down.
- **Hex View**: This switches the display of the current file into hex view. Hex view uses the supplied text plugin (in hex mode) to display the binary contents of the file. Click the button again to switch back to the normal display of the image.
- **Slideshow**: This button enables slideshow mode. Opus will begin showing a slideshow (in the viewer pane) of files in the current folder, starting from the current selection. You can adjust the speed of the slideshow from the **[Viewer / Viewer Pane](/Manual/preferences/preferences_categories/viewer/viewer_pane.md)** page in Preferences.
- **Full Screen**: This command clears the current file from the viewer pane, and re-opens it in the [standalone image viewer](/Manual/additional_functionality/viewing_images/README.md), in full-screen mode. You can leave full-screen mode (and remain in the standalone viewer) by pressing the <kbd>Enter</kbd> key, or press <kbd>Esc</kbd> to close the separate viewer and return to the Lister.
- **Print**: Lets you print the currently viewed image or document.
- **Settings**: This is a shortcut that takes you to the **[Viewer / Viewer Pane](/Manual/preferences/preferences_categories/viewer/viewer_pane.md)** page in Preferences.

### Not all plugins support all functions

Depending on the plugin (if any) used to view a particular file, not all of the above functions may be supported. For example, some plugins may not support rotating the display, and in this case the rotate left and rotate right functions would be unavailable.

### Viewer pane context menu

![](/Manual/images/media/13/viewer_pane_context_menu.png)

The viewer pane also has a context menu - although this too can vary depending on the plugin - accessed by right-clicking on the currently displayed image.

The commands available in the context menu are:

- **View Size**: This lets you change the magnification of the currently displayed image - various preset levels are provided, as well as the two 'fit' modes described above. The option to **Tile** the image is also available.
- **Rotate View**: Rotate the currently displayed image.
- **Gamma Correction**: Modify the gamma correction of the current image - useful if you need to compensate for a darker or brighter monitor.
- **Background Color**: For images with transparency, this lets you switch the background color between black and white (and whatever the default is from Preferences).
- **Select All**: Select the entire image for copying to the clipboard. You can also select areas of the image using the mouse - by default you need to hold the <kbd>Shift</kbd> key down and click and drag to select a rectangular part of the image. If you disable the **Scroll with left mouse button** option on the **[Viewer Pane](/Manual/preferences/preferences_categories/viewer/viewer_pane.md)** Preferences page then you don't need to hold the <kbd>Shift</kbd> key down.
- **Reselect**: If you select a region and then clear the selection, this reselects the area you previously had selected.
- **Copy All**: Copy the entire image to the clipboard. When an area of the image has been selected (as with the **Select All** command, or with the mouse as described above), this command changes to **Copy**, and will only copy the selected area.
- **Print**: Print the currently displayed image.
- **Set As Desktop Wallpaper**: Set the image as your desktop wallpaper. You can choose a number of wallpaper styles from the sub-menu.
- **Properties**: Display the properties of the currently displayed image.
- **Refresh**: Refresh the image. This can be useful if the image or document is being continuously modified in the background (for example, a log file).
- **Use Plugin**: This lets you modify which plugin (if any) is displaying the image. Not all plugins can handle all types of file, of course, but it may be the case that you have multiple plugins installed that can handle the same file, and so this menu lets you experiment with switching between them. You can modify the default order that plugins are used (and also settings that control individual plugins) from the **[Viewer / Viewer Plugins](/Manual/preferences/preferences_categories/viewer/viewer_plugins.md)** page in Preferences.
- **File**: This displays the standard system context menu for the currently displayed file.
