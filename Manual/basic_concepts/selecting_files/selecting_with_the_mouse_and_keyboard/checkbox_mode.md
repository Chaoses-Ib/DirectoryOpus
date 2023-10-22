# Checkbox Mode

Check-box mode is a temporary mode that can be turned on in a file display (it is not a global setting like [single-click mode](single-click_mode.md)).

![](/Manual/images/media/check-box_1.png)

Check-box mode can be turned on with the command in the **Folder Options** menu. By default Check-box mode only remains turned on until you navigate to a new folder, or close that file display (or manually turn it off). If you turn off the **Cancel Checkbox mode when folder is changed** option on the **[Folders / Folder Behaviour](/Manual/preferences/preferences_categories/folders/folder_behaviour.md)** page then the mode will remain enabled even after the folder changes.

![](/Manual/images/media/check-box_2.png) 

As the name suggests, check-box mode causes check-boxes to be displayed next to each item. This changes which files are considered for use in file operations (for example, when you click the **Copy Files** button):

- Normally (when not in check-box mode), functions like **Copy Files** act on all ***selected*** files.
- When in check-box mode, functions like **Copy Files** act on all ***checked*** files.

So in the above screenshot, clicking the **Copy Files** button would copy the files **IMG2100.JPG** and **Spectrum.mp3** to the destination, but not **What's New.docx**.

The main advantage of check-box mode is that it provides selection persistence in the view modes where it is normally very easy to deselect files accidentally. Clicking an empty area of the file display (or indeed, clicking any file) will still cause all files to be deselected, but their *checked states* will not be disturbed. One practical outcome of this is that you can double-click on a file to open it, or select files and drag-and-drop them, without modifying the checked states of any other files in the list. Let's look at a real-world case: imagine that you want to browse through a folder of your holiday photos, to identify the ones you want to send to your friends.

1.  Turn on Check-box mode in the file display, and open the [Viewer pane](../../the_lister/viewer_pane.md) by clicking the button in the toolbar (or press **F7**).
2.  Click on the first file in the folder to select it. It will be displayed in the Viewer pane.
3.  If you want to keep that image, click its check-box with the mouse (or, press the **Space** bar) to check it.
4.  Click on the next image in the folder (or, press **Cursor Down**) to preview the next image, and so on.

At the end of this process, you will have viewed all the images in the folder, and the ones that you wanted to keep will still be checked. You can then use **Copy Files** to copy them to another folder (or alternatively, use the **Edit / Invert Selection** command to invert the check states, and then delete the files you don't want to keep). Without check-box mode you would have had to copy or delete each file as you viewed it - this way, you can concentrate on viewing the images, and then copy or delete them as a batch at the very end.

The main points to keep in mind about check-box mode are:

- When in check-box mode, functions that normally act on selected files instead act on checked files.
- Selection commands like **Edit / Select All** or **Edit / Invert Selection** will affect the checked state of files rather than the selected state.
- You can double-click on a file to open it without losing the check states of other files.
- Drag-and-drop still works on selected files, not checked ones.
- Pressing the **Space** bar toggles the check state of all currently selected files.

There are two commands in the **Edit / Select Other** menu that can be useful when in check-box mode:

- **Selection to Checkboxes**: This command copies the current selection state of each file to its checked state (so selected files will be checked, and unselected files will be unchecked). If the file display is not already in check-box mode when you run this command it will be turned on automatically. This could be useful if you have started selecting multiple files and decide that check-box mode would be a better way to accomplish your task.
- **Checkboxes to Selection**: The reverse of the above command - the current checked state of each file will be copied to its selection state. This is useful if you have checked some files and then want to select them for drag-and-drop.

The [image marking](/Manual/additional_functionality/viewing_images/image_marking.md) function in the [standalone image viewer](/Manual/additional_functionality/viewing_images/RAEDME.md) can make use of check-box mode (if the default option to use a File Collection is turned off). When you tag a file through the viewer in this mode, the file display it came from is automatically placed in check-box mode, and the file in question is checked.
