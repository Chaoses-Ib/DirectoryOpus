# Archive and VFS Plugins

VFS Plugins are third-party extensions to Opus that extended the ability of Opus to list, extract and create archive files. **VFS** is an acronym for Virtual File System and refers to the fact that plugins can also implement whole file-systems (based on a URL-formatted path like *coll://* for [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md)). However by far the most common use for plugins is to add support for archive files to Opus.

This page shows you a list of all archive types handled by your currently installed plugins. The refresh button at the top of the list (![](/Manual/images/media/icons_-_refresh.png)) lets you refresh the list to detect newly added plugins. Plugins must be installed in the *[/home](/Manual/basic_concepts/the_lister/navigation/aliases.md)/VFSPlugins* folder.

![](/Manual/images/media/vfs_plugins.png) 

  
Each individual archive type can be turned on or off using the checkbox button. A plugin may also display an **About** button to display more information about the plugin, and a **Configure** button which will let you configure the plugin itself. These two functions are provided by the plugin itself so the options provided and behavior of the configuration dialogs may be different to those of Opus.

Note that support for Zip files is built-in to Opus, and so there is no entry for Zip in the Plugins list. Instead you can configure Zip options on a [separate page](zip_file_options.md).

When a plugin provides a list of supported archive formats to Opus, those formats are automatically added to the members of the **Archives** [File Type Group](/Manual/file_types/file_type_groups.md), which means you should be able to access them like folders (by double-clicking to display their contents) automatically.
