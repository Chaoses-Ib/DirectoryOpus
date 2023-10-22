# Drop Menu

The Drop Menu tab lets you add commands to the drag and drop menu for files and folders. This is the menu that's displayed when you drag a file with the right mouse button and drop it. For example, Opus uses this system to display the "standard" drop menu items of *Copy Here*, *Move Here* and *Create Shortcut(s) Here*, via the **All files and folders** file type.

![](/Manual/images/media/drop_menu.png) 

  
Configuration of the drop menu for file types is very similar to that of the Context Menu for file types - please see the [Context Menu](context_menu.md) page for a more thorough description of the context menu configuration process. The main difference between the drop menu and the context menu is that the drop menu only supports *Opus-only* context menu items - that is, only **Run an Opus function** or **Sub-menu** items can be added to the drop menu.

As an example of one use for the drop menu, you could add a command to automatically make a softlink (Vista and above only) to a file or folder when you drag it with the right button and drop it somewhere. [Locate](/Manual/file_types/RAEDME.md) the **All files and folders** file type and edit it, and then on the **Drop Menu** tab click the **New** button to add a new menu item.

![](/Manual/images/media/drop_menu_-_softlink.png) 

  
For the **Action** we have specified *Create Softlink Here* - this is the label that will be displayed in the drop menu. The **Type** is set to **Run an Opus function**, and the **Function** definition uses following command:

    Copy MAKELINK=softlink HERE

  
This uses the internal **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command with arguments necessary to create a softlink in the target folder.

If you click **OK** to save the new drop menu command, and then drag and drop a file with the right mouse button, you should see your new command on the drop menu:

  
![](/Manual/images/media/drop_menu_-_results.png)

Creating a softlink requires Administrator privileges so don't be alarmed if you get a UAC prompt as a result of trying this command.

You could also adapt the PNG conversion example shown for the [Events](events.md#convertpng) page for use in the drop menu. For example:

![](/Manual/images/media/drop_menu_-_images.png) 

  
Adding these commands (in a sub-menu) to the drop menu for the **Images** [file type group](../file_type_groups.md) would give you access to a set of convenient image conversion commands simply by dragging an image with the right mouse button and dropping it in the target folder. 

  
![](/Manual/images/media/drop_menu_-_images_results.png) 

  
You can see that as well as the new **Convert Format** menu, the drop menu also shows the **Create Softlink Here** command that we created above. Even though they were added to different file types (**Convert Format** was added to the **Images** group, whereas **Create Softlink Here** was added to the **All files and folders** file type) they are both displayed, because both file types applied to the file we dragged. If you dragged a non-image file, the **Convert Format** menu would not be shown.
