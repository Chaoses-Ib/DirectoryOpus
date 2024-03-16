# Path Field Configuration

The various types of [path fields]() (basic, breadcrumbs, favorites, folder tree, recent) normally operate on the current [source file display](/Manual/basic_concepts/source_and_destination.md) - in a dual-display Lister, the path shown in the field will update as you switch the source from left to right. If desired, these fields can all be configured to control a specific file display. For example, this allows you to have a dual-display Lister with two separate path fields, one for the left and one for the right. You can configure this behaviour by editing the button definition of the field in [Customize](/Manual/customize/RAEDME.md) mode.

![](/Manual/images/media/edit_path_fields.png) 

Select **Customize** from the **Settings** menu, and then right-click on the path field (it will have reverted to a simple frame - see the discussion on [Field Buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/RAEDME.md) for more information on this) and choose **Edit**. The **Args** field in the command editor dialog is used to provide various keywords that define the behaviour of the field. The available keywords are:

- **left**: The path field will always control the left (or top) file display.
- **right**: The path field will always control the right (or bottom) file display.
- **dest**: The path field will always control the destination file display.
- **focus:** If the path field is configured to control a file display other than the source, adding the **focus** keyword as well will cause the focus to be set to that file display automatically (i.e. that file display will become the new source whenever the folder is changed).

For breadcrumbs path fields, you can configure their appearance and behavior via the [Location Bar / Path Fields](/Manual/preferences/preferences_categories/location_bar/path_fields/RAEDME.md) Preferences section.
