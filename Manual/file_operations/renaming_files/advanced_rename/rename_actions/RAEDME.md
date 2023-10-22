# Rename Actions

The **actions** section of the Rename dialog is where you can enable other rename actions besides the primary pattern-based operation (which is controlled by the **[mode](rename_modes/RAEDME.md)** section of the dialog).

![](/Manual/images/media/rename_actions.png)

The options that you enable here will affect your rename operation no matter which of the primary modes you've chosen. The transformations are applied after your pattern-based operation (you can think of the rename procedure as happening from top-to-bottom down the Rename dialog).

**Modify capitalization** lets you automatically modify the capitalization of filenames - the options (with built-in examples) are: *all lower-case*, *ALL UPPER-CASE*, *Capitalize All Words*, *Capitalize first word*, *lower-case extens.ion*, *upper-case extens.ION*.

**Macro operations** lets you define a macro string that can add, remove, copy and paste characters from defined positions in each filename. The macro language is a bit unwieldy to write macros by hand, which is why there's a built-in [macro recorder](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.md) to do the difficult work for you.

**Sequential numbering** lets you add an incrementing number to existing files (or replace the filename entirely with a number). See [Numbering Files](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/numbering_files.md) for more details.

The **Script** option indicates if a rename script has been defined and lets you open the built-in [Rename Script](rename_scripts.md) editor, which lets you write scripts in VBScript, JScript, etc. to completely control the rename process.

More:

[Numbering Files](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/numbering_files.md)  
[Rename Macros](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.md)  
