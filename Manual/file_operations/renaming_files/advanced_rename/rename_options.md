# Rename Options

The **options** section of the Rename dialog contains options which don't affect the new filenames, but instead affect how the rename operation itself behaves.

![](/Manual/images/media/rename_options.png)

**Automatically rename if new filename exists** causes Opus to automatically append an incrementing number to the new filename if the new name is already in use. If turned off and a new filename clashes with an existing one, an error dialog will be shown.

**Rename files in selected sub-folders** lets you make the rename operation operate recursively on files in selected folders rather than renaming the folders themselves. By default a recursive rename operation only renames the files within folders, not the folders themselves. Turn on the Rename folders as well as their contents option if you want to rename folders as well as files in the one operation. The **Show preview of sub-folder contents** causes a preview of the rename operation on the contents of any selected folders to also be shown in the preview list. Note that you can't edit or turn off individual sub-folder files like you can with files at the top-level.

**Rename matching filenames as one** causes Opus to treat multiple files with the same base filename (excluding file extension) as if they were the one file for the purpose of renumbering, wildcard or other batch renames. For example, if you had files called *01012.JPG* and *01012.WAV*, they would be given the same number as part of a renumber rename instead of being numbered sequentially.

**Use preview list to build macros** enables the macro recorder. When turned on, you can click on any "new name" in the preview list and edit the filename directly to record a macro that's then applied to all selected files. If this option is turned off, you can edit filenames individually in the preview list. This is great for making small changes to names which the macro (or other batch operations) may not have got exactly right. Once the name for a file has been edited directly it will be displayed in red and the name is locked in until the rename operation occurs (or until you clear the custom name).
