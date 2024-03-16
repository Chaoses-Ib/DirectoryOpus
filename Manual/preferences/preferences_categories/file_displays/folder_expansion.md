# Folder Expansion

This page contains options relating to [expandable folders](/Manual/basic_concepts/expandable_folders.md) (the feature that lets you expand folders in the file display like you can in the folder tree).

- **Make folders expandable in the file display**: This option enables the folder expansion feature. If this is turned off, folders won't be expandable at all.
- **Clear selections within collapsed folders**: When an expanded folder is collapsed, any items within it that were selected have their selection status cleared (so that when you expand the item again they will be unselected).
- **Collapse sub-folders within collapsed folders**: When an expanded folder is collapsed, any expanded sub-folders within it are also collapsed (so that when you expand the item again they will be unexpanded).
- **Hide expand buttons until a folder is expanded**: This option lets you enable folder expansion without the expander buttons taking up space until they're actually needed. Because the expanders start out hidden, if this option is on the only way to expand a folder is to run the \<nobr\>\<ib:inline-code\>`Go EXPANDBRANCH`\</ib:inline-code\>\</nobr\> command. For example, you can assign that to a hotkey or toolbar button, and use it to initially expand a folder. Once one folder has been expanded the expander buttons will stay visible until the folder is changed or refreshed.

##### Drag and drop

- **Expand folders when dragging over them**: If turned on, you can drag files over an unexpanded folder and it will pop open, letting you drop the files into one of its sub-folders.
- **Collapse after drag (spring-loaded)**: If the previous option is turned on, this option makes the folders that you've dragged over close again after the drop is complete.
- **Expansion delay**: Configure the time (in milliseconds) that you need to hover the mouse over a folder during drag and drop before it expands.
