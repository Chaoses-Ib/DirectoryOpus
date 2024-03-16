# Archive and VFS Plugins

VFS Plugins are third-party extensions to Opus that extended the ability of Opus to list, extract and create archive files. **VFS** is an acronym for Virtual File System and refers to the fact that plugins can also implement whole file-systems (based on a URL-formatted path like \<ib:inline-code\>`coll://`\</ib:inline-code\> for [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md)). However by far the most common use for plugins is to add support for archive files to Opus.

This page shows you a list of all archive types handled by your currently installed plugins. Plugins must be installed in the *[/home](/Manual/basic_concepts/the_lister/navigation/aliases.md)/VFSPlugins* folder. The refresh button at the top of the list lets you refresh the list to detect newly added plugins.

Each individual archive type can be turned on or off using the checkbox button. Some plugins support their own configuration - a "cog" icon next to the item indicates this. Click the cog (or select the plugin and click the **Configure** button above the list) to configure it.

Note that support for zip files is built-in to Opus, and so there is no entry for zip in the plugins list. Instead you can configure zip options on a [separate page](zip_file_options.md).

When a plugin provides a list of supported archive formats to Opus, those formats are automatically added to the members of the **Archives** [file type group](/Manual/file_types/file_type_groups.md), which means you should be able to access them like folders (by double-clicking to display their contents) automatically.
