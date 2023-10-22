# PairedFolder

The **PairedFolder** object is returned by the **[FSUtil](fsutil.md).GetFolderPair** method when you query for a folder's [pair](/Manual/preferences/preferences_categories/frequently_used_paths/paired_folders.md).

Make sure you check the **valid** property before querying any others - if **valid** is **False** it means the folder had no pair, so none of the other properties will exist.

| Property Name | Return Type | Description |
| --- | --- | --- |
| dual | *bool* | Returns **True** if the *Default dual display folder* option is on for the pair. |
| dualnavlock | *bool* | Returns **True** if the *Default Navigation Lock target* option is on for the pair. |
| ifnonexistent | *string* | Returns a string indicating the setting of the *If non-existent* option. Valid values are **gotoparent**, **ignorepair** and **useanyway**. |
| navlock | *bool* | Returns **True** if the *Turn on Navigation Lock automatically* option is on for the pair. |
| path | *object:***[Path](path.md)** | Returns a **[path](path.md)** object which provides the paired folder. |
| primaryonleft | *bool* | Returns **True** if the *Always display primary folder at the left/top* option is turned on. |
| sync | *bool* | Returns **True** if *Default Synchronize target* is turned on for the pair. |
| subfolders | *bool* | Returns **True** if the *Apply Settings to all sub-folders* option is on. |
| valid | *bool* | Returns **True** if the paired folder is valid. |

