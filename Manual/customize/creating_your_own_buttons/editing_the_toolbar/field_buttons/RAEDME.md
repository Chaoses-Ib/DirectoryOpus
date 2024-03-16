# Field Buttons

Field buttons are another special type of button. They are used to place field controls (for example, the location fields) on your toolbars. In Customize mode they appear as a simple frame which you can resize by clicking and dragging the border.

![](/Manual/images/media/field_buttons_-_customize.png)

The above image shows the search field from the default Menu toolbar and the location field from the default File Display Border toolbar. You can see that the search field has grab handles at the right-hand edge, which let you resize the field. The location field does not, because it is set to *Full Width* mode, meaning it will expand to fill all available space on the toolbar.

Once we leave Customize mode you can see that the frames revert to fully functional fields:

![](/Manual/images/media/field_buttons_-_no_customize.png)

Note that the compatibility files button disappeared when leaving Customize mode; this is because when the screenshot was taken the Lister was not currently displaying a folder that has compatibility files, and so the button was automatically hidden. You'll find that many buttons on Opus toolbars can change their state (checked or unchecked, enabled or disabled, hidden or shown) dynamically. If we had navigated to *C:\Program* Files before taking the screenshot the compatibility files button would have been visible.

Field buttons are the only type of button that you can't create manually (by starting with a new button). To add a field button to a toolbar you have to find its entry in the list on the **Commands** page and drag it to the toolbar. Once it is on the toolbar, however, you can change what type of field it is as well as configure certain properties by right-clicking it when in Customize mode.

![](/Manual/images/media/field_buttons_edit.png)

The context menu for a field button lets you configure two options that only apply to fields:

- **Full Width**: If this option is enabled, the field will use all the available space on the toolbar (that is, any space that's not used by another button). If two or more fields on the same toolbar have this flag set, they will share the available space.
- **Restore Focus**: If this option is enabled, pressing the **Enter** key in the field will return focus automatically to the file display.

The **Field Type** sub-menu lets you switch between the various types of field:

- **Content Type**: If folder [content type detection](/Manual/basic_concepts/folder_options/content_types.md) is enabled, displays the current content type format in use. You can also use the drop-down list to instantly switch to one of the defined content type formats.

\<WRAP indent\>![](/Manual/images/media/content_type_field.png)\</WRAP\>

- **Drives**: The [Drive List](/Manual/basic_concepts/the_lister/navigation/drive_buttons_and_lists.md) field is drop-down list of your disk drives. Selecting a drive from the list navigates the source file display to that location.  

\<WRAP indent\>![](/Manual/images/media/drive_list_field.png)\</WRAP\>

- **Filter**: The [filter field](/Manual/basic_concepts/searching_and_filtering/toolbar_filter_fields.md) lets you filter the items visible in the current folder by entering a [wildcard pattern](/Manual/reference/wildcard_reference/pattern_matching_syntax.md).

\<WRAP indent\>![](/Manual/images/media/filter_field.png)\</WRAP\>

- **Label:** A label field has no function other than to display a static label. You can use it to provide a label for other controls or just to display a static text string on a toolbar.

\<WRAP indent\>Label fields in drop-down menus are drawn in a bold font and left-aligned to stand out visually from the other items in the menu.\</WRAP\>

\<WRAP indent\>![](/Manual/images/media/image079.png)\</WRAP\>

- **Path (Basic)**: The basic path (location) field is a minimalist text field that displays the current path and lets you type a new path to navigate in the Lister. By default this field controls the current source file display, but you can [configure](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/path_field_configuration.md) it to specify the display it is linked to.

\<WRAP indent\>![](/Manual/images/media/path_field_basic.png)\</WRAP\>

- **Path (Breadcrumbs)**: The [breadcrumbs](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.md) path (location) field is a powerful navigation tool that provides instant access to prior locations in the current path. This field has [lots of configurable options](/Manual/preferences/preferences_categories/location_bar/path_fields/RAEDME.md) that can modify its appearance and behaviour.

\<WRAP indent\>![](/Manual/images/media/path_field_crumbs.png)\</WRAP\>

- **Path (Favorites List)**: The favorites list path field combines the basic path field with a drop-down menu of your [favorite folders](/Manual/basic_concepts/the_lister/navigation/favorites.md), which you can navigate to by selecting them from the drop-down. By default this field controls the current source file display, but you can [configure](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/path_field_configuration.md) it to specify the display it is linked to.

\<WRAP indent\>![](/Manual/images/media/path_field_dropdown.png)\</WRAP\>

- **Path (Folder Tree)**: The folder tree path field combines the basic path field with a drop-down list containing the folder tree hierarchy leading to the current location. This lets you navigate to previous folders in the tree from the drop-down. By default this field controls the current source file display, but you can [configure](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/path_field_configuration.md) it to specify the display it is linked to.

\<WRAP indent\>![](/Manual/images/media/path_field_dropdown.png)\</WRAP\>

- **Path (Recent List)**: The recent list path field combines the basic path field with a drop-down menu of your [recently visited folders](/Manual/basic_concepts/the_lister/navigation/recent_and_history_lists.md). By default this field controls the current source file display, but you can [configure](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/path_field_configuration.md) it to specify the display it is linked to.

\<WRAP indent\>![](/Manual/images/media/path_field_dropdown.png)\</WRAP\>

- **Search Field**: The search field lets you search the current folder using the indexed [Windows Search](/Manual/basic_concepts/searching_and_filtering/windows_search.md) system.

\<WRAP indent\>![](/Manual/images/media/search_field1.png)\</WRAP\>

- **Spacer**: A spacer field has no function other than to take up room on the toolbar - it's used to right-justify toolbar elements.

- **Thumbnail Size**: The thumbnail size field lets you dynamically resize thumbnails in the current folder. It will be hidden when the Lister is not in thumbnail mode.

\<WRAP indent\>![](/Manual/images/media/thumbnail_size_slider.png)\</WRAP\>

\<WRAP indent\>By default, the slider affects all folder tabs in the window if it's on a normal toolbar, and just the side it's over if it's on a Location Bar toolbar. You can change this by editing the field and adding \<ib:inline-code\>`both`\</ib:inline-code\>, \<ib:inline-code\>`source`\</ib:inline-code\>, \<ib:inline-code\>`dest`\</ib:inline-code\>, \<ib:inline-code\>`left`\</ib:inline-code\>, or \<ib:inline-code\>`right`\</ib:inline-code\> to the *Args* string. (\<ib:inline-code\>`both`\</ib:inline-code\> differs from the default in that it only affects the visible tabs, not inactive ones.)

By default the slider will set the thumbnail size using the aspect ratio configured in Preferences; however, if you edit the field and add \<ib:inline-code\>`preserve`\</ib:inline-code\> to the *Args* string, it will preserve the current aspect ratio (this would only be useful if the aspect ratio has been changed manually using the \<ib:inline-code\>`Set THUMBNAILSIZE`\</ib:inline-code\> command). If a side is also specified, put a comma between the two arguments; e.g. \<ib:inline-code\>`left,preserve`\</ib:inline-code\>.\</WRAP\>

See the [Editing The Toolbar]() section for more information on how to edit toolbar fields.

More:

[Path Field Configuration](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/path_field_configuration.md)  
[Breadcrumbs Configuration](/Manual/preferences/preferences_categories/location_bar/path_fields/RAEDME.md)  
[Filter Field Configuration](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/filter_field_configuration.md)  
[Drive List Configuration](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/drive_list_configuration.md)  
