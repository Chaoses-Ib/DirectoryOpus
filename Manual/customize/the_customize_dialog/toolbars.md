# Toolbars

The Toolbars page displays a list of all your toolbars, and lets you create new ones, delete existing ones, and turn them on or off. You can also change various appearance settings for individual toolbars from this page.

![](/Manual/images/media/customize_-_toolbars.png) 

The checkboxes indicate whether a toolbar is currently turned on or off. Use the toolbar buttons to manipulate the toolbars: ![](/Manual/images/media/favorites_-_add.png) (create a new toolbar), ![](/Manual/images/media/filters_-_duplicate.png) (duplicate an existing toolbar), ![](/Manual/images/media/filters_-_rename.png) (rename toolbar), ![](/Manual/images/media/favorites_-_delete.png) (delete toolbar) and ![](/Manual/images/media/toolbars_-_float_button.png) (float toolbar). Note that the [default toolbars](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/RAEDME.md) cannot be deleted or renamed. The **Reset to Defaults** command only applies when one of the default toolbars is selected.

When you select a toolbar from the list (and it is turned on), you are able to edit a number of settings on the right-hand side of the page. These are grouped into two sections.

The **Background** section controls the background color and image of individual toolbars. By default toolbars are set to use the *Standard Toolbar Image*, which makes it easy to change the image for all toolbars at once (you only have to change one setting) and means that [Lister Themes](/Manual/basic_concepts/the_lister/themes/RAEDME.md) can also change the background image of toolbars. However you can make a toolbar use any background image that you have added to the list on the Preferences [Display / Images](/Manual/preferences/preferences_categories/display/images.md) page. The options in this section are:

- **Color**: Turn this on if you want to specify a solid background color for the toolbar. If this is turned off the default color from Preferences will be used.
- **Image**: Turn this on if you want to select a background image from the drop-down. To use an image on a toolbar you must first add it to the list of [Images](/Manual/preferences/preferences_categories/display/images.md) in Preferences. You can also specify whether the image is stretched, tiled or shared across the Lister.  If **Image is inherited by submenus** is turned on then any drop-down menus from the toolbar (and any of their child menus) will display the same background image as the parent toolbar.

The **Images & Labels** section lets you override the image and label settings of individual buttons on the toolbar. Toolbar buttons can define their own image and label state, as well as image size, but the options in this section let you override them and instantly turn all labels or images on or off for the whole toolbar.

- **Image Size**: Specify the image size (*small* or *large*) for buttons on the toolbar. If you select *default* then the buttons' own settings will be used.
- **Image State**: Specify the image state (*on* or *off*) for all buttons on the toolbar, or select *The **Import** and **Export** commands in the File menu for this page let you export the selected toolbar so you can share it with other people, or import toolbars you have received from others.*to use each individual button's own settings.
- **Label State**: Specify the label state (*on* or *off*) for all buttons on the toolbar, or select *default* to use the buttons' own settings.
- **Label Color**: Turn this option on to specify the label color for buttons on the toolbar. The color specified on the [Colors and Fonts](/Manual/preferences/preferences_categories/display/colors_and_fonts.md) page of Preferences will be used if turned off.
- **Font**: Turn this option on if you want to specify a font for button labels. If turned off the font configured on the [Colors and Fonts](/Manual/preferences/preferences_categories/display/colors_and_fonts.md) page of Preferences will be used instead.

If the **Always enable this toolbar's keys in Listers** option is turned on, any hotkeys defined within the toolbar will be active in Listers whether or not the toolbar itself is currently visible. This is used for the two main default toolbars (*Menu* and *Operations*), so that even if you turn them off, standard keys like **Ctrl+A** (for *Select All*) will still function.

From this page you can float a toolbar (other than one of the default toolbars) by selecting it from the list and clicking the *Float Toolbar* button (![](/Manual/images/media/toolbars_-_float_button.png)). See the [Controlling Floating Toolbars](/Manual/additional_functionality/floating_toolbars/controlling_floating_toolbars.md) page for information on controlling the appearance and behavior of floating toolbars.

Double-clicking a toolbar in the list will cause any instances of that toolbar to briefly flash. This can be a handy way to find where a toolbar is located. Any instances of that toolbar that are floating are also displayed and will flash briefly to identify them.

The **Import Toolbar **and **Export Toolbar **commands in the *File* menu for this page let you export the selected toolbar so you can share it with other people, or import toolbars you have received from others. The **Factory Reset** command lets you reset any of the default toolbars to their factory settings - you can also do this by right-clicking the toolbar itself (in a Lister) to access its context menu.
