# Viewer Plugins

Viewer Plugins are third-party extensions to Opus that extended the ability of Opus to view, convert, and access metadata in images and other file types.

This page shows you a list of all your currently installed plugins. If plugins offer a configuration dialog of their own, you can access it from here. You can also change the order of precedence for plugins, which is useful if you have two plugins that can handle the same type of file.

![](/Manual/images/media/viewer_plugins.png)

The plugin list displays your installed plugins. The toolbar buttons can be used to change the order (![](/Manual/images/media/favorites_-_up.png) - move up, and ![](/Manual/images/media/favorites_-_down.png) - move down) and refresh the list to detect newly added plugins (![](/Manual/images/media/icons_-_refresh.png)). Plugins must be installed in the *[/home](/Manual/basic_concepts/the_lister/navigation/aliases.md)/Viewers* folder.

You can also turn plugins off using the checkboxes next to their names; this lets you turn off plugins for file types you don't use which may speed up the process when viewing files.

![](/Manual/images/media/plugin_config.png)

When you select a plugin in the list it expands to show some information about that plugin - normally a description of the plugin and a list of the file extensions that it handles. A plugin may also display an **About** button to display more information about the plugin, and a **Configure** button which will let you configure the plugin itself. These two functions are provided by the plugin itself so the options provided and behavior of the configuration dialogs may be different to those of Opus.

When you view an image in Opus that Opus doesn't handle itself, Opus will move through the plugin list from top-to-bottom to try to find a plugin that can handle the file. If you have two plugins installed that can handle the same type of file you can use the up and down buttons to change the order of precedence and so control which plugin is used to handle the file.

Some plugins are a special type known as *catch-all* - these are plugins that by definition can handle (in some way or another) any type of file. For example, the supplied **Text** plugin can ultimately handle any type of file because it displays a raw hex-view of any file that isn't plain text. Catch-all plugins can not be moved up from the bottom of the list as they must be checked last after other, more specific, plugins have been tried.
