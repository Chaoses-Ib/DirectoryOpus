# OtherMeta

The **OtherMeta** object is retrieved from the **[Metadata](metadata.md).other** property. It provides access to miscellaneous information about the file or folder.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
autodesc</td><td>

*string*</td><td>
An automatically generated description string for the item. This is the same string that is shown in the Description column in a Lister. Opus automatically generates the description for various types of files using the other metadata in ways that make the most sense.
</td></tr><tr><td>
dircount</td><td>

*int*</td><td>

For a folder, the size of which has been calculated via **[GetSizes](../../command_reference/internal_commands/getsizes.md)** or similar, this provides the number of sub-folders directly underneath the folder.
</td></tr><tr><td>
dircounttotal</td><td>

*int*</td><td>

Similar to **dircount**, this provides the total number of sub-folders underneath the folder (this is a recursive count - it includes sub-sub-folders, sub-sub-sub-folders, etc.)
</td></tr><tr><td>
filecount</td><td>

*int*</td><td>

For a folder, the size of which has been calculated via **[GetSizes](../../command_reference/internal_commands/getsizes.md)** or similar, this provides the number of files directly located in that folder.
</td></tr><tr><td>
filecounttotal</td><td>

*int*</td><td>

Similar to **filecount**, this provides the total number of files in the folder and all its sub-folders, sub-sub-folders, etc.
</td></tr><tr><td>
foldercontents</td><td>

*string*</td><td>

For a folder, the size of which has been calculated via **[GetSizes](../../command_reference/internal_commands/getsizes.md)** or similar, this returns a string giving a summary of the contents of the folder.
</td></tr><tr><td>
nsdesc</td><td>

*string*</td><td>
A description automatically generated for the item by its parent virtual file system.
</td></tr><tr><td>
rating</td><td>

*int*</td><td>
Returns the user-assigned rating for this file or folder.
</td></tr><tr><td>
target</td><td>

*object:***[Path](path.md)**</td><td>

Returns a **[Path](path.md)** object representing the target path of shortcuts and links.
</td></tr><tr><td>
target_type</td><td>

*string*</td><td>

Returns a *string* indicating the type of the link (*unknown*, *linkfile*, *dosfile*, *url*, *junction*, *softlink*).
</td></tr><tr><td>
usercomment</td><td>
string</td><td>
Returns the user-assigned description for the file or folder.
</td></tr></tbody>
</table>

