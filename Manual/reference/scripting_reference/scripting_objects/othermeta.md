# OtherMeta

The **OtherMeta** object is retrieved from the **[Metadata](metadata.md).other** property. It provides access to miscellaneous information about the file or folder.

| Property Name | Return Type | Description |
| --- | --- | --- |
| autodesc | *string* | An automatically generated description string for the item. This is the same string that is shown in the Description column in a Lister. Opus automatically generates the description for various types of files using the other metadata in ways that make the most sense. |
| dircount | *int* | For a folder, the size of which has been calculated via **[GetSizes](../../command_reference/internal_commands/getsizes.md)** or similar, this provides the number of sub-folders directly underneath the folder. |
| dircounttotal | *int* | Similar to **dircount**, this provides the total number of sub-folders underneath the folder (this is a recursive count - it includes sub-sub-folders, sub-sub-sub-folders, etc.) |
| filecount | *int* | For a folder, the size of which has been calculated via **[GetSizes](../../command_reference/internal_commands/getsizes.md)** or similar, this provides the number of files directly located in that folder. |
| filecounttotal | *int* | Similar to **filecount**, this provides the total number of files in the folder and all its sub-folders, sub-sub-folders, etc. |
| foldercontents | *string* | For a folder, the size of which has been calculated via **[GetSizes](../../command_reference/internal_commands/getsizes.md)** or similar, this returns a string giving a summary of the contents of the folder. |
| nsdesc | *string* | A description automatically generated for the item by its parent virtual file system. |
| rating | *int* | Returns the user-assigned rating for this file or folder. |
| target | *object:***[Path](path.md)** | Returns a **[Path](path.md)** object representing the target path of shortcuts and links. |
| target_type | *string* | Returns a *string* indicating the type of the link (*unknown*, *linkfile*, *dosfile*, *url*, *junction*, *softlink*). |
| usercomment | string | Returns the user-assigned description for the file or folder. |

