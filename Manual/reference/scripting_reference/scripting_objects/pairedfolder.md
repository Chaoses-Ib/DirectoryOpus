# PairedFolder

The **PairedFolder** object is returned by the **[FSUtil](fsutil.md).GetFolderPair** method when you query for a folder's [pair](/Manual/preferences/preferences_categories/frequently_used_paths/paired_folders.md).

Make sure you check the **valid** property before querying any others - if **valid** is **False** it means the folder had no pair, so none of the other properties will exist.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
dual</td><td>

*bool*</td><td>

Returns **True** if the *Default dual display folder* option is on for the pair.
</td></tr><tr><td>
dualnavlock</td><td>

*bool*</td><td>

Returns **True** if the *Default Navigation Lock target* option is on for the pair.
</td></tr><tr><td>
ifnonexistent</td><td>

*string*</td><td>

Returns a string indicating the setting of the *If non-existent* option. Valid values are **gotoparent**, **ignorepair** and **useanyway**.
</td></tr><tr><td>
navlock</td><td>

*bool*</td><td>

Returns **True** if the *Turn on Navigation Lock automatically* option is on for the pair.
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.md)**</td><td>

Returns a **[path](path.md)** object which provides the paired folder.
</td></tr><tr><td>
primaryonleft</td><td>

*bool*</td><td>

Returns **True** if the *Always display primary folder at the left/top* option is turned on.
</td></tr><tr><td>
sync</td><td>

*bool*</td><td>

Returns **True** if *Default Synchronize target* is turned on for the pair.
</td></tr><tr><td>
subfolders</td><td>

*bool*</td><td>

Returns **True** if the *Apply Settings to all sub-folders* option is on.
</td></tr><tr><td>
valid</td><td>

*bool*</td><td>

Returns **True** if the paired folder is valid.
</td></tr></tbody>
</table>

