# Viewing Images

Opus has two main image viewers. Both can be used to view images, movies, documents and other formats for which a plugin exists.

##### Viewer pane

There's the integrated [Viewer Pane](/Manual/basic_concepts/the_lister/viewer_pane.md), which is embedded within a Lister:

![](/Manual/images/media/13/viewer_pane.png)

##### Standalone viewer

There's also a standalone (floating) image viewer.

![](/Manual/images/media/13/standalone_viewer.png)

The main difference is the [Viewer Pane](/Manual/basic_concepts/the_lister/viewer_pane.md) is tied to a Lister whereas the standalone viewer acts almost like a separate utility. The standalone viewer also has basic image editing functions which the viewer pane does not.

##### Accessing the standalone viewer

You can access the standalone viewer in several ways:

- If the **Use internal picture viewer** option on the **[File Operations / Double-click on Files](/Manual/preferences/preferences_categories/file_operations/double-click_files/RAEDME.md)** page in Preferences is turned on, double-clicking on a recognized image file will open it in the standalone viewer.

- The **Slideshow** button on the default toolbar will launch a slideshow of all images in the current folder, using the standalone viewer. The speed of the slideshow is controlled from the **[Slideshow](/Manual/preferences/preferences_categories/viewer/standalone_viewer/slideshow.md)** page in Preferences.

- The internal **[Show](/Manual/reference/command_reference/internal_commands/show.md)** command will display selected files in the standalone viewer. This command is available on the drop-down menu attached to the **Slideshow** button.  
- From outside of Opus, you can use the \<ib:inline-code\>`d8viewer.exe`\</ib:inline-code\> or \<ib:inline-code\>`dopusrt.exe /show`\</ib:inline-code\> commands to open files with the Opus viewer.

##### Options for the standalone viewer

There are a number of options that control the appearance and behaviour of the standalone viewer. These can be found in the **[Viewer](/Manual/preferences/preferences_categories/viewer/RAEDME.md)** category in Preferences. By default, the viewer will:

- Auto-size to fit every picture - as you step through images, the window will resize if needed to display the picture.
- Open centered on the current monitor.
- Display a frame around the picture (as in the above screenshot).
- Show or hide the scrollbars while viewing images.
- Automatically build a list of all other pictures in the folder, when opened via a double-click on an image file (with an additional option for the list to wrap-around when you reach the start or end).
- Automatically rotate images to compensate for the EXIF orientation tag, saved by most digital cameras.

These options can all be changed from Preferences.

More:  
[Viewer Mouse, Keys and Toolbar](/Manual/additional_functionality/viewing_images/viewer_keys_and_toolbar.md)  
[Image Marking](/Manual/additional_functionality/viewing_images/image_marking.md)  
