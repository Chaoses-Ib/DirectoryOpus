# Archive Options

This page contains various options that apply to archive handling in general, irrespective of the archive format.

- **Open archives as read-only by default**: If this is turned on, when you navigate to an existing archive it will automatically be treated as read-only by Opus. You will not be able to make changes to the contents of the archive without turning off [read-only mode](/Manual/file_operations/creating_archives/zip_files/read-only_mode.md). (This works with the internal Zip support as well as 7z, RAR, TAR, etc. archives handled by the official Archives plugin. Support within third-party VFS plugins may vary.)
- **Packed column units**: When you are viewing the contents of a zip file in a file display you can add several zip-specific columns to the file display, including the *Packed* column. This column displays the compressed or "packed" size of files within the archive. You can use this option to change the units the *Packed* column displays file sizes in (*bytes*, *KB *or *auto* - which means Opus chooses the most appropriate unit automatically).

### Auto-extract

Auto-extract lets you run installers directly from an archive by double-clicking the setup file.

- **Auto-extract archive contents on double-click**: Turn this on to have Opus automatically extract the full contents of the archive to a temporary folder when you double-click on a file within the archive. This is most useful for archives containing installers - if you double-click on the enclosed *Setup.exe* program you would normally want all the other files of the archive extracted as well in order for the installer to run successfully.
- **Prompt before extracting**: Before the contents of the archive are automatically extracted, Opus will prompt you for confirmation.
- **Extensions**: This specifies the file extensions that auto-extract works on. Normally you wouldn't add anything to this list other than **.exe** for executable files.
- **Qualifier key**: You can optionally use the drop-down to have auto-extract only take effect when the specified qualifier key is held down.
