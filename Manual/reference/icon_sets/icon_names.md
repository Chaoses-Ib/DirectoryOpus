# Icon Names

Every icon in an icon set must have a name. The name is used for two things – it lets the user search for icons in the *Select Icon* dialog, and it is stored in the toolbar configuration and used internally by Opus to identify which icon the user has configured for a given button.

Opus supports multiple active icon sets at any given time. When a toolbar button is configured to use an icon, Opus searches the list of installed icon sets for an icon of that name. The first icon found with the specified name is the one that is shown. For example, a toolbar button may beset to use an icon called “copy”. Opus will search its list of icon sets, looking for an icon in the desired size (small or large) called “copy”. The first matching icon that is found is the one that is used.

Opus uses many hard-coded icon names internally to refer to the default functions. For example, “copy”, “move”, “delete”, “rename”, “print”, “play” and “undo” are some of the more than 200 hard-coded icon names. If you want your icon set to be able to replace the default toolbar buttons - *without the user having to specifically configure their buttons to use your icons* – you need to make sure you use the same names as Opus.

However, you are free to use any name you like for your icons. For example, you may wish to create an icon set that provides icons suitable for a source code control program. There are no internal Opus icons that are relevant to this, so your intention would not be to replace the internal icons, but to augment them. Therefore, you would pick names for your icons that don’t match the internal ones.

For a full list of the hard-coded icon names that Opus uses, you can generate a template .xml file using the *Save Icon Set Template* menu command on the Toolbar Icons page in Preferences.
