# Status Bar

The status bar at the bottom of the each file display is primarily used to display basic statistics about the current folder. Like most things in Opus, it's fully configurable.

##### The default status bar

![](/Manual/images/media/13/status_bar_1.png) 

This is an example of the default status bar. The information presented (from left to right) is:

- Number selected / Total number of folders
- Number selected / Total number of files
- Different file extensions selected (and how many of each)
- Number of hidden items (if any items are currently [hidden by filters](../searching_and_filtering/README.md))
- Total size of all selected items / Total size of all items (this includes the size of any selected folders only if their [sizes have been calculated](/Manual/basic_concepts/folder_sizes.md))
- [Current format](../folder_options/identifying_the_current_format.md) indicator and menu (![](/Manual/images/media/13/info.png))
- Space free on current drive
- Percentage of used space on current drive (as a bar chart)

##### Configuring the status bar

You can use the **[File Displays / Status Bar](/Manual/preferences/preferences_categories/file_displays/status_bar.md)** page in Preferences to configure the information displayed in the status bar. Using the various available status bar codes it is possible to configure some quite complicated status bar displays, including detailed information about selected files, various bar charts and more.

The options on that Preferences page also let you change the status bar to appear at the bottom of the Lister instead of the file display (so, for example, you can have one single file display at the bottom of the window that applies only to the active file display instead of each display having its own).

##### Status bar tooltips

Some status bar elements will show you tooltips with more information when you hover over them:

- Hidden item indicators show the names of the first few hidden files and folders, so you can quickly see if anything of interest is hidden. Click them to toggle [Show Everything](../searching_and_filtering/show_everything.md) mode on and off.
- The ![](/Manual/images/media/13/info.png) format indicator shows you where the current folder format comes from, to help you determine how to affect changes to the format. It also has a right-click context menu that lets you quickly change the current [folder format](../folder_options/README.md).
