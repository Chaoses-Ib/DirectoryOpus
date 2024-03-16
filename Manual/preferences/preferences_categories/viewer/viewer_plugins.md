# Viewer Plugins

Viewer Plugins are third-party extensions to Opus that extended the ability of Opus to view, convert, and access metadata in images and other file types. Plugins must be installed in the *[/home](/Manual/basic_concepts/the_lister/navigation/aliases.md)/Viewers* folder.

When you view an image in Opus that Opus doesn't handle itself, Opus will move through the plugin list from top-to-bottom to try to find a plugin that can handle the file. If you have two plugins installed that can handle the same type of file you can use the up and down buttons on this page to change the order of precedence and so control which plugin is used to handle the file.

This page shows you a list of all your currently installed plugins. If plugins offer a configuration dialog of their own, you can access it from here using the "cog" icon displayed to the right of the plugin name (or the **Configure** button above the list).

You can also turn individual plugins off using the checkboxes next to their names; this lets you turn off plugins for file types you don't use which may speed up the process when viewing files.

When you select a plugin in the list some information about that plugin is shown below the list - normally a description of the plugin and a list of the file extensions that it handles.

Some plugins are a special type known as *catch-all* - these are plugins that by definition can handle (in some way or another) any type of file. For example, the supplied **Text** plugin can ultimately handle any type of file because it displays a raw hex-view of any file that isn't plain text. Catch-all plugins can not be moved up from the bottom of the list as they must be checked last after other, more specific, plugins have been tried.
