# Filenames

This page contains options relating to how filenames are displayed.

- **Display localized folder names**: Some system folders have translated names that differ from their actual names on disk. For example, the *C:\Program Files* directory is displayed on French systems as *C:\Programmes* even though its real name never changes. With this option on Opus will display the localized name for such folders instead of the real name in the filesystem.
- **Hide the .lnk extension for shortcuts**: Shortcut files have the extension **.lnk** - if you turn this option on, the **.lnk** extension will be hidden in file lists.
- **Hide the .url extension for Internet shortcuts**: Similarly, Internet shortcuts have the extension **.url**, and this option lets you hide them.
- **Hide other extensions as specified in the Windows registry**: It's possible to mark individual file extensions as hidden via the Windows registry - if you do this (or use a tool that does it for you), this option makes Opus respect those settings.
- **Modify display of all-uppercase filenames**: This lets you modify the display of filenames that are all upper-case, for example legacy files copied from non-long filename filesystems like FAT-formatted drives. The filenames themselves are not altered, just how Opus displays them in the file list.
- **Preserve file extensions when truncating names**: If a filename is too wide to be shown in the filename column, it's normally truncated at the end. This option keeps the file extension visible and truncates the *stem* preceding the extension.
- **Strip Unicode Left-to-Right and Right-to-Left characters**: Unicode directional characters can be used to obscure a file's true extension by making it appear in the middle of the name instead of at the end. With this option turned on, Opus strips those out so you always see the file's true extension.
