# Tracking and Undoing File Operations

There are two features in Opus that help you keep track of changes you have made to files and folders.

### Undo

The **Undo** command can (usually) be used to undo the most recent action. Most actions can be undone - for example, if you rename a group of files incorrectly with a wildcard, you can undo the rename fairly easily. File deletes, however, can not be undone unless the delete was done to the recycle bin. You can find the **Undo** command in the **Edit** menu in a Lister (or press <kbd>Ctrl+Z</kbd>).

![](/Manual/images/media/13/undo_history.png) 

Opus maintains a history of undoable functions. From the **Undo List** sub-menu, you can see the ten most recent actions, and undo any of them by selecting it from the list. Selecting the **More...** command from that sub-menu displays the [Utility Panel](/Manual/basic_concepts/the_lister/utility_panel.md), showing the **Undo Log** page. This page displays a full list of undoable actions, and you can undo one, many or all actions from this page at the click of a button.

### File Log

While the undo log only shows the most recent undoable actions in the current session, the file log** **maintains a persistent log of all file operations (undoable or not). You can access the **File Log** from the [Utility Panel](/Manual/basic_concepts/the_lister/utility_panel.md), or select the command directly from the **Help** menu.

By default the file log records the last 1000 file operations. You can see what sort of action occurred, the file involved, when it happened, and in the case of a copy or move, the destination folder.

![](/Manual/images/media/13/file_log_example.png)

The file log can be extremely useful at times - if you've ever found that a file you knew was there has mysteriously disappeared, you can often find out what happened to it through the log. You can use the filter field to search for a file by name or path.

The **Save** button at the top of the log lets you export the log as a text file - useful if it's quite large and you want to search it in a text editor. You can configure the maximum size of the log, and control which operations are recorded, from the **[File Operations / Logging](/Manual/preferences/preferences_categories/file_operations/logging.md)** page in Preferences.
