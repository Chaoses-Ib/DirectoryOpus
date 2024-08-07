## Events

The **Events** tab lets you configure functions for file types that are initiated by various mouse events - double-click and drag and drop events. For example, you can configure Opus to run a different program for files when they're double-clicked and the **Shift** key is held down, or when they're double-clicked with the middle mouse button (if you have one). It's also possible to use this system to have different double-click behavior to Explorer - so that double-clicking a file in Opus can behave quite differently to double-clicking it in Explorer.

![](/Manual/images/media/filetypes_-_events.png) 

The above screenshot shows an example of some events that have been configured for the **Images** [file type group](../file_type_groups.md). The events that you can configure are:

- **Drag-and-drop**: What happens when you drag and drop a file to another folder.
- **Left double-click**: What happens when you double-click a file with the left mouse button.
- **Middle double-click**: What happens when you double-click a file with the middle mouse button.

These three events can also be configured separately depending on whether the **Alt**, **Ctrl** or **Shift** keys are held down. There are no right button double-click events as the right button is used for [Context Menus](context_menu.md). You can also add items to the drag and drop context menu (the menu displayed when you drag a file with the right mouse button) on the [Drop Menu](drop_menu.md) tab.

Whenever one of the above events occurs, Opus searches your configured file types looking for a configured action. File types are searched in the following order:

1.  The specific file type for that file (e.g. for a **.jpg** file this might be the **JPEG Image** file type)
2.  The file type group that contains that file extension (e.g. **Images**)
3.  The **Recognized images** file type if the file is a recognized image file
4.  The **All files** file type (or for a folder, **All folders**)
5.  The **All files and folders** file type.

The first, most specific, file type found that has a function defined for that event is the one used.

To edit the event for a file type, select the event from the list and click the **Edit** button at the bottom of the page (or double-click the event in the list). The event editor is a variant of the standard command editor, so please see the [Command Editor](/Manual/customize/creating_your_own_buttons/command_editor/README.md) page for instructions on how to define a command.

You can also right-click on the items in the events list to display a context menu for the event. This context menu lets you use **Copy** and **Paste** to copy the definition from one event to another.

The events system can be very useful; with a bit of careful thought and configuration it's possibly to really streamline your workflow. To take the above screenshot as an example, four events have been configured for the **Images** group (meaning they will act on any file type added to that group).

1.  ![](/anchor/convertpng/)The **Drag-and-drop + Ctrl** event has been configured to convert images to PNG format when you hold the **Ctrl** key and drop them in a folder.

![](/Manual/images/media/event_-_dropctrl.png)

The function used for this is **Image CONVERT=png**. This invokes the [Image Conversion](/Manual/additional_functionality/image_conversion/README.md) function and specifies an output format of PNG. Because the output format has been specified on the command line, the image conversion dialog will not appear - instead the dropped file will be immediately saved to the target folder in PNG format.

1.  The **Left double-click** event has been configured to open the file in the internal Opus viewer when the file is double-clicked.

![](/Manual/images/media/event_-_dblclk.png)

This event calls the internal **[Show](/Manual/reference/command_reference/internal_commands/show.md)** command to view the image using the [standalone image viewer](/Manual/additional_functionality/viewing_images/README.md). This lets you double-click images in Opus to preview them quickly in its own viewer, but doesn't have any effect on what happens when you double-click an image file outside of Opus.

1.  The **Left double-click + Ctrl** event has been configured to open the file in Photoshop when the file is double-clicked and the **Ctrl** key is held down.

![](/Manual/images/media/event_-_dblclkctrl.png)

This event runs the external function **"C:\Program Files\Adobe\Adobe Photoshop CS5 (64 Bit)\Photoshop.exe" %1** to open the file in Photoshop. The **%1** [control code](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md) is used to pass the filename to **Photoshop.exe**.

1.  Finally, the **Middle double-click** event has been configured to open the file in the standard Windows image viewer when the file is double-clicked with the middle mouse button.

![](/Manual/images/media/event_-_middleclk.png)

This events runs the external function **C:\Windows\System32\rundll32.exe "C:\Program Files\Windows Photo Viewer\PhotoViewer.dll", ImageView_Fullscreen %1** which invokes the Windows photo viewer. The name of the file is passed to the application using the **%1**[control code](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md).

 
