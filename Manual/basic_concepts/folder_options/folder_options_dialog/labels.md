# Labels

![](/Manual/images/media/folder_options_-_labels.png)

The **Labels** tab on the Folder Options dialog lets you define wildcard labels and label filters that are only active when this folder format is used. It lets you apply labels to files and folders under specific folders without having to use them globally.

Use the toolbar buttons at the top to assign new labels: 

- ![](/Manual/images/media/filter_label.png) **Create a new label filter**: You can use [filters](/Manual/file_operations/copying_moving_and_deleting_files/filtered_operations/RAEDME.md) to assign labels based on attributes other than filename or location - they can be based on [any criteria supported by the filter system](/Manual/file_operations/copying_moving_and_deleting_files/filtered_operations/filter_clause_types.md), although you should keep in mind that the filter will be compared against every file in every directory you visit - potentially slow filter clauses like *Contains* should be used with caution.

![](/Manual/images/media/label_filter.png) 

The above screenshot shows a label filter that will color red any files or folders that are under SVN control and have been modified. It uses a shell column provided by [TortoiseSVN](http://tortoisesvn.net/) to match the SVN status.

- ![](/Manual/images/media/labels_4.png) **Create a new wildcard label**: Labels files and folders based on their names or locations. You can specify a pattern using standard [Opus wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) or [regular expressions](/Manual/reference/wildcard_reference/regular_expression_syntax.md), and choose whether to restrict the assignment to files, folders or both.

The **Match Full Path** checkbox decides if the pattern needs to match the whole path or just the folder or file name at the end of the path. This doesn't matter for a wildcard like **\*.(doc\|docx)** for matching **.doc** and **.docx** files, since the extension is going to be at the end of both the full path and the name. It can matter with a wildcard like **A\*.doc** where in full-path mode it would only match **.doc** files on **A:\\** whose names start with any letter, and in name-only mode it would match **.doc** files whose names start with the letter **A** in any drive or folder.

Wildcards here can also use the **grp:** syntax to match file extensions against members of a [file type group](/Manual/file_types/file_type_groups.md). For example, this would color anything in the **Images** group purple:

![](/Manual/images/media/wildcard_label.png) 

- ![](/Manual/images/media/label_folder.png) **Assign label to a specific folder path**: Lets you assign a label to a folder by its path. That is, the label will be attached to the path and name of the folder, not the folder itself.

- ![](/Manual/images/media/label_file.png) **Assign label to a specific file**: Assign a label to a file by its path. That is, the label will be attached to the path and name of the file, not the file itself.

By default filter and wildcard labels assignments will "stack" on top of each other. One label could change the color of an icon, and another could change the icon itself. You can use the **Stop on match** option on both wildcard labels and label filters to prevent this from happening. Note that filter and wildcard label assignments can be rearranged to control their priority. The **up** ( ![](/Manual/images/media/label_up.png) ) and **down** ( ![](/Manual/images/media/label_down.png) ) buttons let you move label assignments above or below each other.

The labels themselves are configured on the **[Favorites and Recent / Labels](/Manual/preferences/preferences_categories/favorites_and_recent/file_and_folder_labels.md)** page in Preferences (click the **Edit labels** link to be taken there automatically). See the [Labels](/Manual/file_operations/labels.md) page for information on the labels system.
