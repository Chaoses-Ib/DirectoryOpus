# Zip Files

Unlike 7-Zip, RAR and other archive formats that are implemented via a plugin system, Opus includes built-in support for Zip files. Although you don't really need to care about the distinction, it's worth mentioning because you may wonder otherwise why it seems like Zip archives are treated differently in some ways to other archive formats. For example, options affecting Zip files are found on a separate page in Preferences to other archive formats.

While you can normally work with Zip files and other archive formats the same way, there are a few special features provided for Zip files that don't apply to the other formats:

- **Zip Comment**: Explicit support is provided for setting the embedded [comment](/Manual/file_operations/creating_archives/zip_files/zip_comment.md) inside Zip archives.
- **Read-Only mode**: A special mode that applies only to archive files - they can be opened as [read-only](/Manual/file_operations/creating_archives/zip_files/read-only_mode.md) to prevent accidental changes to the contents of the archive.
- **Self-Extracting Zip Files**: Opus can convert Zip files to a [self-extracting](/Manual/file_operations/creating_archives/zip_files/self-extracting_zip_files.md) format - an executable file that automatically extracts its contents when run.

Opus also uses Zip files internally for some of its own file formats. For example, if you [backup your configuration](/Manual/preferences/backing_up_and_restoring_preferences.md), Opus creates a **.ocb** file - this is really a Zip archive, and if you rename the file to **.zip** you can open it like a normal archive.

More:

[Zip Comment](/Manual/file_operations/creating_archives/zip_files/zip_comment.md)  
[Read-Only mode](/Manual/file_operations/creating_archives/zip_files/read-only_mode.md)  
[Self-Extracting Zip Files](/Manual/file_operations/creating_archives/zip_files/self-extracting_zip_files.md)  
