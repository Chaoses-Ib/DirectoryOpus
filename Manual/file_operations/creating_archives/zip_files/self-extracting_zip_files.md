# Self-Extracting Zip Files

Opus lets you convert a Zip archive into what's called a self-extracting archive. This turns an archive file (which needs another program to decompress it) into an executable program that you can send to people. When they run the program, an easy-to-use interface will guide them through extracting the contents of the archive.

Now that Windows itself comes with built-in support for Zip files self-extracting archives are not as widely used as they once were, but there are still some uses for them.

To create a self-extracting archive, you must first [create the source Zip archive](). You can use the **[Add to Archive](../add_to_archive_dialog/RAEDME.md)** dialog to create a Zip archive and convert it to self-extracting format in one step, or you can create the archive and then convert it separately using the context menu command that Opus adds automatically to the context menu for **.zip** files.

This context menu can be disabled through the [Archive Context Menu](/Manual/preferences/preferences_categories/zip_and_other_archives/archive_context_menu.md) Preferences page, so if you don't see it when you right-click on a Zip file you may need to go and turn it on.

##### Self-Extracting Archive options

The **Create Self-Extracting Archive** dialog gives you several options that control the final self-extracting archive:

- **From**: Displays the name of the Zip archive you are converting.
- **To**: Specifies the path of the **.exe** file the conversion process will create. This defaults to the same location and name as the source archive, but with a **.exe** instead of **.zip** extension.
- **Name**: This lets you configure a name that is displayed in the title bar of the self-extractor when it's run.
- **Custom instructions**: Select an external text file (**.txt**) to provide instructions or a message that will be displayed in the self-extractor when it's run. If you don't provide a file then default instructions are displayed.
- **Custom image**: Select an external image file that is displayed on the left-hand side of the self-extractor window. If you don't select this option a standard image is used. If you turn this option on but don't select an image file then no image at all will be used, which can reduce the size of the final **.exe** file slightly.
- **Default path for extraction**: This lets you specify a location that will be used as the default path the files in the archive are extracted to when the self-extractor is run. The end-user will still be able to modify the destination path; this is simply a default.
- **Auto-run after extraction**: If your archive contains any executable programs, you can select one from the drop-down list to have that file automatically run after the archive has been extracted. For developers, you could use this to create a simple "installer" that extracts several files and then runs an included Setup.exe-type program to perform the actual installation.

Once you have chosen your parameters, click the **OK** button to perform the actual conversion process. You should be left with a **.exe** file slightly larger than the original Zip archive.

##### The self-extractor

When someone runs your self-extracting archive, they will see a window similar to this:

![](/Manual/images/media/13/sfx.png)

From this window you can deduce the parameters we set when creating the extractor:

- The image on the left of the window is the default - we didn't specify anything for **Custom image** when creating the self-extractor.
- The displayed text is the result of specifying a **Custom instructions** file.
- We didn't specify a **Default path** for extraction, so the default behavior is to extract to the temporary folder.
- We also didn't specify an **Auto-run after extraction** file, so that option is disabled.

The **Open folder to view files** option is user-controllable; if they select that then a window (from their default folder browser) will be opened automatically to show the contents of the extracted archive.

The extraction function handles UAC automatically. If the user opts to extract to a UAC-protected location (like **C:\Program Files**) they will be asked to elevate to approve the action.
