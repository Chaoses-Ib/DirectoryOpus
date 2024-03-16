# Styles

The Lister Styles system lets you configure different configurations of [Lister elements]() and quickly switch between them. Conceptually they are similar to [layouts](layouts/RAEDME.md), except that a style is applied to modify the appearance of an existing Lister - it doesn't cause a new Lister to be opened like a layout does.

For example, you can define a style that opens the [viewer pane](viewer_pane.md) and the [metadata pane](metadata_pane.md), loads a [toolbar set](toolbars/toolbar_sets.md), and closes the [folder tree](navigation/folder_tree.md) all in one operation.

Styles can also cause a new folder to be read, multiple [folder tabs](tabs/RAEDME.md) to be created and can also modify the [format](../folder_options/RAEDME.md) of the currently displayed folder.

##### Pre-defined styles

The styles that Opus pre-defines are:

- **Commander**: A dual file display with no tree, similar to the "classical" appearance of some older Windows file managers.
- **Dual Horizontal**: Dual file displays, dual trees. The layout of the file displays is horizontal (one above the other).
- **Dual Vertical**: Like Dual Horizontal, only laid out with the file displays next to each other.
- **Explorer**: Standard "Explorer" style, with a single tree and a file display.
- **Filmstrip**: Designed for viewing photos - a narrow file display in thumbnails mode, showing a single "strip" of thumbnails, and the viewer pane open to preview the selected image.
- **Images**: Like Filmstrip except with a wider file display.
- **Metadata**: Designed for editing metadata, this style opens both the viewer pane and the metadata pane.
- **Single**: A single file display with no tree.

These styles are just examples; of course you are free to modify or delete them, and you can also create your own.

##### Creating a style

Use the [Layouts and Styles / Styles](/Manual/preferences/preferences_categories/layouts_and_styles/styles.md) Preferences page to create and manage styles.

##### Applying a style to the Lister

The **Lister** dropdown menu shows a list of styles. Select one from the list to load it. You can also right-click the styles in the list to update them with the current Lister settings.

You can also use the `Prefs STYLE` raw command - this is useful if you want to create [hotkeys](/Manual/customize/the_customize_dialog/keys.md) to quickly switch between multiple Lister configurations.

##### Style tabs

Another way to switch styles is with the style tabs. You can add these to a toolbar from the **[Commands](/Manual/customize/the_customize_dialog/commands.md)** tab of the *Customize* dialog. Type `tabs` into the search field and look for the **Lister Styles - Tabs** command, and then drag it to a toolbar to add it.
