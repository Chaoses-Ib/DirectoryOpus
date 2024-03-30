# Advanced

This page contains a list of what are considered "advanced" options. They're generally esoteric settings most users don't need to know about let alone change.

Each option has a name and a value. The values can be Boolean (true/false), numeric, a string, or a choice from a drop-down list. To edit an option's value, double-click the existing value, or select the option and press <kbd>F2</kbd>. When an option isn't set to its default value, it's displayed in bold.

When you select an option a description of it will be shown at the bottom of the page. Items marked with an asterisk are global settings - they affect all users of the computer. You can reset an option to its default value by selecting it and clicking the **Reset** button at the bottom.

If you're looking for a particular option, you can use the search field at the top to search for it by name or description. The **Hide unchanged settings** checkbox to the right of the search field can be used if you want to see only the settings you have modified from their default values.

<table>
<thead><tr><th>

**Category: Behavior**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
Option</td><td>

** Global? **</td><td>
Description
</td></tr><tr><td>

**clipboard_datestamps**</td><td>
</td><td>
Names like "Clipboard Image.bmp" and "Clipboard Text.txt" are used when pasting image or text data from the clipboard into new files, with a numeric suffix added if required to make them unique. Turning on this option adds a YYYY-MM-DD HH-MM-SS datestamp to the start of these filenames. This helps keep them in order when pasting and converting multiple pieces of data, and when selecting them in standard File Open dialogs which don't sort the names properly otherwise.
</td></tr><tr><td>

**clipboard_text_encoding**</td><td>
</td><td>
Specifies the default text encoding to use when pasting text from the clipboard to a file.
</td></tr><tr><td>

**compress_collections**</td><td>
</td><td>

Compress [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md) to save disk space. If turned off, File Collections will be saved as uncompressed XML files - if you have a lot of files in a collection, this can make the files take up a lot of space.
</td></tr><tr><td>

**config_backup_name**</td><td>
</td><td>

Template used to generate the default name for configuration backups. You can still edit the name manually when doing the backup, but this changes what it is initially.

The template supports `D#`, `T#` and `A#` prefixes for dates and times (as described [here](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.md)) and environment variables. Note that to use date and time codes you must enclose them in `{}` brackets (e.g. `{D#yyyy-MM-dd}`).

(Opus 13.3.4 and above:) Local time is used by default, but you can prefix with `UTC#` to use UTC instead (e.g. `{UTC#T#HH-mm}`).
</td></tr><tr><td>

**dblclk_distance**</td><td>
</td><td>
Maximum distance (in pixels) the mouse cursor can move for a double-click to register.
</td></tr><tr><td>

**display_release_history**</td><td>
</td><td>
When turned on, the Release History page in the help file will open automatically the first time Directory Opus is used after installing a new version. This helps you learn about new features, fixes and other changes in the new version. Turn the option off to prevent the release history page from appearing automatically.
</td></tr><tr><td>

**drag_distance**</td><td>
</td><td>
Distance in pixels that the mouse cursor needs to move to initate a drag and drop. Set this to 0 if you want to disable drag and drop completely.
</td></tr><tr><td>

**find_extension_func**</td><td>
</td><td>

On Windows XP, Opus registers a [Search Handler](http://msdn.microsoft.com/en-us/library/bb776834(v=vs.85).aspx) that lets you access the Opus Find function from the Start Menu. You can use this option to configure the command that Opus runs in response to the search handler. If not specified, the default [Find](/Manual/reference/command_reference/internal_commands/find.md) command is used.
</td></tr><tr><td>

**find_unique_collections**</td><td>
</td><td>

Don't let simultaneous [Find](/Manual/basic_concepts/searching_and_filtering/find_files/README.md) operations use the same collection for results. The Find function defaults to presenting its results in the *Find Results* [File Collection](/Manual/basic_concepts/virtual_file_system/file_collections/README.md). If you have two or more Find operations running in parallel, this option causes the name of the output File Collection for the second and subsequent tasks to be modified to be unique, so that the results are not intermingled.
</td></tr><tr><td>

**flatview_folder_filters**</td><td>
</td><td>

Enable filtering out of sub-folders in [Flat View](/Manual/basic_concepts/flat_view.md). By default the quick filter (i.e. the filter set by the [Filter Bar](/Manual/basic_concepts/searching_and_filtering/filter_bar.md)) is not applied to folders when the file display is in Flat View. The reason for this is that when a folder is filtered from the list, all its contents are automatically filtered as well, and this may lead to undesired results. The Filter Bar has a checkbox option displayed when the file display is in Flat View mode that lets you turn folder filtering on or off, and you can use this option to control the default state of that checkbox (that is, if you normally do want the quick view filter to apply to folders as well as files in Flat View, turn this option on.)
</td></tr><tr><td>

**go_up_always_back**</td><td>
</td><td>

The `Go UP` command normally re-reads the parent folder, even if you had previously visited it and it is in the history list, and you can add the **BACK** argument (i.e. **Go UP BACK**) to cause Opus to use the history if possible (preserving file selections) when going to the parent folder. If you turn on this option then **Go UP** will always behave as if it had the **BACK** argument specified as well.
</td></tr><tr><td>

**image_locate_services**</td><td>
</td><td>

Lets you configure the image location services used by the `Image LOCATE` command. Each line consists of the keyword used to refer to the service, an equals sign, and a URL that will be opened in your default web browser. The insert codes `%lat%` and `%lon%` are used to pass through the latitude and longitude of the image.
</td></tr><tr><td>

**layout_string**</td><td>
</td><td>

This option lets you define the name that is given to [Lister Layouts](/Manual/basic_concepts/the_lister/layouts/README.md) that you drop on your desktop from the [Layouts](../layouts_and_styles/layouts.md) page in Preferences. You must specify a string that contains the code `%1` - this code is replaced with the name of the layout in the generated shortcut. If nothing is specified for this option, the default is `Layout '%1'`.
</td></tr><tr><td>

**manual_sort_names**</td><td>
</td><td>

Lets you define additional [manual sorting](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md) orders. Opus can remember more than one manual sorting order and you can switch between your named orders easily. For example, you might have a manual sort order that you use at work and another that you use at home. You must enter each name on a line by itself. If you don't specify any names there will only be one, unnamed, manual sort order available.
</td></tr><tr><td>

**navlock_warn_verbose**</td><td>
</td><td>

With Navigation Lock on, entering a relative path on one side which the other side cannot mirror causes a warning to appear over the file display. By default, when **navlock_warn_verbose** is **True**, this warning is long and explains that you can return to the previous folder to get the two sides back in sync, as well giving options to manually re-sync on the current folder pair or to turn off Navigation Lock entirely. If you set **navlock_warn_verbose** to **False**, a shorter, less obtrusive message is displayed. If you already understand how Navigation Lock works and have read the longer message many times already, switch to the shorter message.
</td></tr><tr><td>

**pinyin_support**</td><td>
</td><td>
Opus has some support for Pinyin (a method of entering Chinese characters using a Western keyboard). By default, if Opus is running in Chinese, the FAYT and filter bar both support Pinyin for searching/filtering. This option lets you override the automatic setting and specifically enable or disable Pinyin support.
</td></tr><tr><td>

**powermode_singledrag**</td><td>
</td><td>

[Power mode](/Manual/basic_concepts/the_lister/view_modes.md) file displays have persistent selection by default - when you click on an unselected item, it selects it but does not automatically deselect any other selected items. Normally when you click on an item and drag it out, all other selected files are also dragged as well. When this option is on, if you click on a single file and drag it to the left or right, only that file will be part of the drag - any other selected files will not be.
</td></tr><tr><td>

**powershell_exe**</td><td>
</td><td>
Lets you can specify the default PowerShell executable to use. For example, you may wish to make the default PowerShell menu items open PowerShell 7 instead of Windows PowerShell.
</td></tr><tr><td>

**rename_default_focus**</td><td>
</td><td>

Selects which field in the [Rename](/Manual/file_operations/renaming_files/advanced_rename/README.md) dialog gets input focus by default - the *Old Name* or *New Name* field. Rename scripts can override this setting.
</td></tr><tr><td>

**save_button_editor_pos**</td><td>
</td><td>

Save the default position of [Command Editor](/Manual/customize/creating_your_own_buttons/command_editor/README.md) dialogs. If you turn this option on Opus will remember the position of the Command Editor when it is closed, and use that saved position the next time one is opened. If turned off, the Command Editor will appear centered over its parent window.
</td></tr><tr><td>

**searchfield_autostart**</td><td>
</td><td>

Lets you control how long after you stop typing a search from the Lister search field will automatically begin. If set to 0 this uses the value configured for the FAYT on the [Find-As-You-Type](/Manual/preferences/preferences_categories/filtering_and_sorting/find_as_you_type/README.md) page.
</td></tr><tr><td>

**scroll_lock**</td><td>
</td><td>

If the **Scroll Lock** key is turned on the cursor keys will scroll the file display without changing the focus item.
</td></tr><tr><td>

**search_warn_nonindexed**</td><td>
</td><td>
When true, if you use Windows Search on a folder which is not indexed, and the search takes more than a few seconds, Opus will display a banner warning you that the search may be slow because the folder is not indexed. If off, the warning will not be displayed. (This has no effect on Opus's built-in Find Files functionality. Find Files is independent from Windows Search indexing and does not display similar banners.)
</td></tr><tr><td>

**setwallpaper_file**</td><td>
</td><td>

The `Properties SETWALLPAPER` command can be used to set a selected image file as the desktop wallpaper. By default the selected file is copied to your documents folder, but you can override the location by specifying a full path and filename for this option. The filename specified must end in either **.bmp** or (in Vista and above) **.jpg**.
</td></tr><tr><td>

**single_click_rename**</td><td>
</td><td>

If you have [single-click mode](/Manual/basic_concepts/selecting_files/selecting_with_the_mouse_and_keyboard/single-click_mode.md) enabled, and the file display is in [Details mode](/Manual/basic_concepts/the_lister/view_modes.md) with full-row selection enabled in [Preferences](../file_display_modes/details_mode.md), it is normally not possible to initiate [inline rename](/Manual/file_operations/renaming_files/inline_rename.md) using the mouse, because a click anywhere on the line would open the item. With this option enabled you can however initiate inline rename using the mouse - once the entry is selected by hovering, you can click anywhere on the line *other* than the filename to begin rename.
</td></tr><tr><td>

**slow_dblclk_rename**</td><td>
</td><td>

Set this to **False** to disable the standard functionality that lets you enter inline rename mode via a "slow double-click" (clicking an already selected file or folder outside of the double-click time). If slow double-click rename is disabled you can still use the **F2** key to enter inline rename mode.
</td></tr><tr><td>

**status_metadata_trigger**</td><td>
</td><td>

Controls when the status bar, if displaying selected or total media duration (time lengths), may trigger the calculation of that data, if nothing else in the file display has triggered it already.

Calculating media duration involves opening and parsing data from inside each file individually, and this can take some time and tie up the disk or network, particularly when there are a lot of files.

If durations have already been calculated for one of the columns in the file display (e.g. the **Duration** column), the setting is moot since the status bar will re-use those calculations. The setting only changes whether the status bar on its own can trigger the calculations.

If the status bar definition does not include any of the [media duration codes](/Manual/reference/status_bar_codes/codes_for_music_and_video_duration.md) -- i.e. **{smp3}** or **{tmp3}** -- then the setting is also moot, since the status bar won't trigger calculation of data it is not interested in.

The default setting is **Never**, meaning the status bar never triggers calculations on its own, and only shows duration information when it has been calculated by something else.

Selecting the **Always** setting means the status bar will trigger duration calculations in all situations.

Selecting the **Always, except Flat View and Collections** setting means the status bar can trigger duration calculations, except when [Flat View](/Manual/basic_concepts/flat_view.md) is enabled or when in [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md). Flat View and Collections often involve a large number of files, making them a worst case.
</td></tr><tr><td>

**styles_update_previous**</td><td>
</td><td>

If you have made changes to a Lister's appearance (by either opening or closing user interface elements manually, or via a [Lister Style](/Manual/basic_concepts/the_lister/styles.md)), the `Prefs STYLE` command lets you return the Lister to its initial appearance. If you turn this option on then what is considered to be the "previous" style is updated whenever a new Lister Style is chosen (and so `Prefs STYLE=^prev` would from then on reset the Lister to that style rather than its initial layout).
</td></tr><tr><td>

**tab_click_nofocus**</td><td>
</td><td>

Clicking on a [folder tab](/Manual/basic_concepts/the_lister/tabs/README.md) to bring it to the front normally activates that file display and makes it the source. If this option is on then clicking a tab in the destination file display would leave the source/destination status unchanged.
</td></tr><tr><td>

**utility_panel_autoshrink**</td><td>
</td><td>
This setting can be used to make the Utility Panel automatically shrink down to just its heading after performing a Find, Duplicate Files of Synchronize operation. Click the setting to open a menu where you can turn auto-shrink on or off for each operation.
</td></tr><tr><td>

**wheel_acceleration**</td><td>
</td><td>
Opus normally applies a small amount of acceleration when scrolling in file displays using the mouse wheel, but you can disable it using this option if desired.
</td></tr><tr><td>

**wordbreak_char_names**</td><td>
</td><td>

This lets you specify one or more characters that will be used as "word break" characters in edit fields when editing filenames (e.g. in inline rename). Word break characters affect where the cursor stops when you press the **Ctrl+Left** or **Ctrl+Right** keys. A space is always treated as a word break.
</td></tr><tr><td>

**wordbreak_char_paths**</td><td>
</td><td>

This lets you configure additional word break characters in edit fields when editing paths (e.g. in the [Breadcrumbs path field](/Manual/basic_concepts/the_lister/navigation/breadcrumbs_location_field.md)). The standard path delimiters  (**:/\\**) are always treated as a word break.
</td></tr><tr><td>

**wsl_distribution**</td><td>
</td><td>
If you have more than one WSL distribution installed this option lets you control which one Opus uses to launch WSL commands.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**Category: Compatibility**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
Option</td><td>

** Global? **</td><td>
Description
</td></tr><tr><td>

**convert_descriptions**</td><td>
</td><td>

Convert old description files to the *descript.ion* format. Unless you are migrating from an extremely old version of Directory Opus you should never need to set this.
</td></tr><tr><td>

**def_func_cd_sourcedir**</td><td>
</td><td>

Use the current source directory as the default current directory when launching programs from buttons that don't specify a current directory. The default for such functions is to set the current directory to the *C:\Windows\System32* directory for security reasons.
</td></tr><tr><td>

**direct2d**</td><td>
</td><td>

Controls how Direct2D is used to render certain parts of the UI. Direct2D is used in some places to provide better performance or better quality rendering.

**Normal** is the default option, enabling Direct2D and allowing the operating system to decide whether to use hardware (GPU) or software (CPU) rendering.

**Force CPU rendering** can be selected if you think there is a problem with your GPU hardware or drivers and want to force Direct2D to render everything on your CPU instead.

**Disable** can be chosen to prevent Direct2D from being used at all.

At the time of writing, the option affects the progress dialog's speed graph.
</td></tr><tr><td>

**dlldir_security**</td><td>
</td><td>
This option, enabled by default, prevents Opus from loading DLLs from the current working directory. This reduces the risk of "binary planting" exploits which can trick your computer into running untrusted software when you open things like photos or music from folders in which someone has hidden a malicious DLL.

Turning this option off will reduce your security but may be needed if it causes problems with poorly written shell extensions or other third party software which is installed on your computer. (Such software is typically only tested with Windows Explorer, which does not traditionally used the more secure mode which Opus uses by default.)

This option only affects Opus and, potentially, the software you launch from Opus. It is not a system-wide setting (although there is one if you want to be even more secure; search the web for CWDIllegalInDllSearch for more information).

This option cannot be modified when running from a portable USB install.
</td></tr><tr><td>

**dragdrop_async**</td><td>
</td><td>

When files are dropped on Opus from another program, Opus will usually handle them in the background so that its window remains responsive. If the program you dragged from supports the Windows API for asynchronous drag & drop then this should never be a problem; however, a large number of programs fail to support the API.

When **dragdrop_async** is on, Opus will attempt to handle *all* drops in the background, bending the rules if it has to, unless it detects a drop from a program known to have problems with this. If the option is off, Opus will be more strict and will only handle drops in the background for programs that explicitly support it.

If you run into problems when dragging files to Opus from certain programs, try turning this option off to see if it improves compatibility. The downside is that you may sometimes have to wait for drops to complete before you can continue using the window you dropped on.
</td></tr><tr><td>

**flush_com_libraries**</td><td>
</td><td>

By default, Opus is fairly agressive at asking COM libraries (typically shell extension DLLs) to unload when they are no longer needed. This can cause crashes in components which say they can unload incorrectly when they are still running code within the process. Switching this setting to **False** may reduce problems with those faulty components.
</td></tr><tr><td>

**function_default_async**</td><td>
</td><td>

By default, a function that contains a single command will run [asynchronously](/Manual/customize/creating_your_own_buttons/synchronous_and_asynchronous_functions.md), and functions that contain two or more commands will run [synchronously](/Manual/customize/creating_your_own_buttons/synchronous_and_asynchronous_functions.md). This option lets you override this behaviour and make all functions (single or multiple commands) run asynchronously by default.
</td></tr><tr><td>

**global_explorer_replacement**</td><td>
Global</td><td>

[Explorer Replacement](/Manual/basic_concepts/explorer_replacement.md) mode is normally a per-user setting, but if you turn this option on then the Explorer Replacement mode setting will be global for all users of the machine. This may improve the ability of Opus to intercept some calls to Explorer, but normally you would leave this turned off.
</td></tr><tr><td>

**mp3_custom_comments**</td><td>
</td><td>

The MP3 ID3v2 tag used for comments is not rigidly defined, and different third-party tools often use their own form of this tag. You can use this option to make Opus write COMM tags with the specified descriptions, to provide compatibility with these tools when using the [Metadata pane](/Manual/basic_concepts/the_lister/metadata_pane.md). For example, MediaMonkey labels its COMM tag as **Songs-DB_Custom1**, so you would put this string into the **mp3_custom_comments** value to make Opus MP3 comments compatible with MediaMonkey. If you use multiple tools you can add multiple comment descriptions, one on each line, and Opus will write a separate COMM tag for each.
</td></tr><tr><td>

**no_async_icons**</td><td>
</td><td>

File types for which icons should not be retrieved asynchronously. Normally Opus retrieves file icons on a background thread for greater performance, but we have found occasionally that the icons for some file types can not be generated successfully in the background. Multiple file extensions should be separated with a semi-colon. Note that the following extensions are automatically blocked for background icon extraction: **.msg;.oft;.xnk**
</td></tr><tr><td>

**patch_edit_control_dpi**</td><td>
</td><td>
Lets you disable the Edit control patch that fixes vertical centering under high DPI. This is in case the patch causes problems with future versions of Windows.
</td></tr><tr><td>

**patch_text_apis**</td><td>
</td><td>

When set to *True* (the default), Opus will patch some of the Windows text rendering and measuring APIs with the aim of making them use consistent font kerning. This should make character spacing look better and more consistent throughout the program. It should also prevent issues where a string of latin characters are spaced differently if a non-latin character is added to or removed from the end, which can cause text to overflow its bounds. However, since this setting modifies operating system APIs (only within dopus.exe), it could cause compatibility issues with third party code which runs inside of Opus. If you see text rendering or layout issues within Opus, see if turning this off helps, and please report your findings via the Directory Opus tech support forum.
</td></tr><tr><td>

**regex_style**</td><td>
</td><td>

Set the style of [Regular Expressions](/Manual/reference/wildcard_reference/regular_expression_syntax.md) used by Opus. The default is *TR1 ECMAScript*, but you can change this to revert to the original regular expression style supported by older versions of Opus. You would really only want to do this if you had a large number of saved [Rename](/Manual/file_operations/renaming_files/advanced_rename/README.md) presets that for some reason don't work with the new flavor of regular expression.
</td></tr><tr><td>

**zip_large_file_support**</td><td>
</td><td>

Enable support for Large Zip files. Large Zip files support individual items, and archives, that are more than 4 GB in size, and more than 65536 individual items in an archive. Large Zip support is enabled by default but if you need to maintain compatibility with legacy archives you can turn this option off. Opus will always read Large Zip files even if this option is turned off - it merely controls the type of archive that Opus creates.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**Category: Cosmetic**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
Option</td><td>

** Global? **</td><td>
Description
</td></tr><tr><td>

**collection_icon_default**</td><td>
</td><td>

Custom default icon for individual file collections which don't match any of the other types of collections.

This setting changes the default icon. You can also change a particular collection's icon via its properties dialog.

You can specify the path to a standalone .ICO file (e.g. `C:\MyIcon.ico`), or specify icons within .EXE and .DLL files using numeric IDs to select a particular icon (e.g. `/system/imageres.dll,101`).
</td></tr><tr><td>

**collection_icon_find**</td><td>
</td><td>

Similar to **collection_icon_default**, but specific to collections generated for Find Results and Search Queries.
</td></tr><tr><td>

**collection_icon_flickr**</td><td>
</td><td>

Similar to **collection_icon_default**, but specific to collections generated for Flickr Synchronization.
</td></tr><tr><td>

**collection_icon_marked**</td><td>
</td><td>

Similar to **collection_icon_default**, but specific to Marked Pictures collections generated by marking images in the viewer.
</td></tr><tr><td>

**collections_icon**</td><td>
</td><td>

Custom icon for the [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md) root folder.

This only affects the actual "File Collections" root folder. The other settings above cover individual collections of various types.

You can specify the path to a standalone .ICO file (e.g. `C:\MyIcon.ico`), or specify icons within .EXE and .DLL files using numeric IDs to select a particular icon (e.g. `/system/imageres.dll,101`).
</td></tr><tr><td>

**context_menu_icon_set**</td><td>
</td><td>

Some context menus contain items which Opus generates automatically, and where you do not have an opportunity to change which size or style of icons are used, other than by moving an icon set to the top of the list and affecting *all* toolbar and menu icons. Since you may wish to use a smaller icon set in context menus than everywhere else, this setting allows you to specify another set to use instead of the normal one. Opus will use this setting when generating context menu items for adding to and extracting from archives. Note that this only applies when the menu is shown inside of Opus; the similar menu in Explorer does not use icon sets in the first place.

The name should match the icon set's XML “name” attribute, *not* its “display_name”. For example, if the icon set is defined with `<iconset name="flat_small"> ... <display_name>Small Icon Set (Flat)</display_name>` then you should type “flat_small” into the setting, and not “Small Icon Set (Flat)”.
</td></tr><tr><td>

**custom_network_folder_icons**</td><td>
</td><td>

When set to *True*, individually customized folder icons can be displayed in the location field and folder tabs when on network drives. (On local drives, and within the file display itself, custom folder icons are always supported, subject to the **Show generic icons for...** setting under **[Preferences / Folders](../folders/README.md)**.)

Turning this on may cause slower performance, or even temporary freezes, if you have folder tabs pointing to very slow or inaccessible network drives. Custom folder icons are usually configured via a folder's Properties dialog, but Windows hides the option for network folders, probably for performance reasons and because you need to ensure the icon paths you specify are accessible to all network clients. You can still manually create the custom icon metadata, or copy a locally customized folder to a network drive. So it is possible to have custom folder icons on network drives, but it is rare, and you should only turn this on if you are using them.
</td></tr><tr><td>

**glass_status_bar**</td><td>
</td><td>

When set to *True*, draws the status bar using the Windows "glass" effect for its background. This looks good on Windows 7 but is fairly pointless on newer versions of Windows.

This setting has no effect unless glass is enabled system-wide (i.e. Desktop Window Composition is available), and the **Keep status bars at the bottom of the Lister** is turned on under **Preferences / Display / Status Bar**.
</td></tr><tr><td>

**gloss_and_gradients**</td><td>
</td><td>

Enable gloss and gradient effects in various user interface elements. Turn this off if you prefer a flatter, more boring appearance.

When set to *Automatic*, a flat and simple look is chosen if on Windows 8 or above, and a shiny look with gradients is chosen on Windows 7.
</td></tr><tr><td>

**grid_lines_first_last**</td><td>
</td><td>

Changes how horizontal grid lines are drawn in the file display. This is primarily to help visually separate the file display column header from the files and folders below it, since some Windows versions draw the header without a bottom edge and with the same background color as everything below it.

If set to **First** or **Both** with solid grid lines, the alternating pattern begins on the first item instead of the second. If set to **First** or **Both** with thin grid lines, an extra grid line is drawn before the very first item, just under the column header (but only if visual styles are used for the file display, and line spacing is 0 or 1).

Setting this option to **Last** or **Both** with thin grid lines adds an additional grid line after the very last item, instead of skipping it. The **Last** option no effect on solid grid lines.

In all cases, the setting has no effect on items under group headers, since group headers have their own lines already.
</td></tr><tr><td>

**no_contextmenu_fix**</td><td>
</td><td>

When the "Office 2003" style is selected for [toolbars](../toolbars/toolbar_appearance.md), Opus has to perform some magic to make owner-draw third party context menu extensions look good. If you find that Opus' magic isn't quite up to par, you can disable it with this option.
</td></tr><tr><td>

**progress_smoothing**</td><td>
</td><td>
Smooth progress bar updates on Vista and above. Turn off for lag-free progress bars which jump immediately when updated.
</td></tr><tr><td>

**resize_grips**</td><td>
</td><td>
By default Listers do not have visible resize grips, for improved cosmetics, especially in dual-horizontal with inline status bars. Grips can be turned back on using this option if you so desire.
</td></tr><tr><td>

**thumb_48x48_icons**</td><td>
</td><td>

Enables the use of 48x48 icons for thumbnails and tiles. This has trade-offs:

- If the setting is off, icons which have neither 256x256 nor 32x32 versions will look bad.
- If the setting is on, icons which have neither 256x256 nor 48x48 versions will look bad. 32x32 icons are far more common than 48x48 icons, so the setting is off by default.

(The exact icon sizes vary with system DPI settings. The sizes used here are for the standard DPI.)

Each icon can contain various versions of itself in different sizes. Regardless of this setting, Opus always prefers the high-quality 256x256 versions of icons which have them. For icons which do not have 256x256 versions, Opus requests a 32x32 version if the setting is off and a 48x48 version if the setting is on.

When an icon contains neither of the requested sizes, one of its other sizes is selected and scaled to fit. This is done by Windows itself and the scaling is not done to a high quality, with resized icons becoming blurry and messy. Windows will not say which sizes of an icon are available without scaling and will not indicate when an icon had to be scaled to fit a requested size, so the quality of the result is determined by the requested size and some icons will look bad either way.

(This option affects the icons for things like .EXE files. It does not affect actual .ICO files because Opus is able to generate thumbnails for them without these problems and compromises.)
</td></tr><tr><td>

**window_corners**</td><td>
</td><td>
Allows you to override the operating sytem's default style of window corners. "Automatic" uses the standard for your version of Windows. You can also choose from square corners and two sizes of round corners.

It can also affect the intensity of the shadow the OS draws around the active window.

(Only available on Windows 11 or later.)
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**Category: Filesystem**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
Option</td><td>

** Global? **</td><td>
Description
</td></tr><tr><td>

**copy_allow_delegation**</td><td>
</td><td>

When **True**, allows Opus to delegate details of how files are copied to Windows.

Windows provides a very-high-level API for copying files which is optimized in arcane and undocumented ways and which is also what device manufacturers tend to test and optimize their hardware and drivers against. You usually cannot beat this API for performance and compatibility; at best you can equal it.

Opus also has its own custom file-copying code which works at a slightly lower level and, crucially, in situations which are not simple file-to-file copies. This custom code is often the same speed as the very-high-level API, but there are situations where it is slower (e.g. with particular devices or network configurations that are highly sensitive to buffer size or other parameters).

By default, Opus uses the very-high-level API for normal file-to-file copies. In situations where that API cannot be used, Opus automatically falls back on its own custom code. These situations include copying into or out of archives and FTP sites, copying while preserving sparse data, and splitting and joining files.

If you set **copy_allow_delegation** to **False**, Opus will always use its custom file-copying code, even in situations where it does not have to. You might want this in rare situations where the Windows file-copying API is slower for some reason, or where you want to force the use of non-buffered I/O. In general, we don't suggest you modify this setting.

The `Copy DELEGATE` argument can be used to override this setting on individual buttons, hotkeys, etc.
</td></tr><tr><td>

**copy_buffer_size**</td><td>
</td><td>

Buffer size used by the custom file-copying code. Units can be KB, MB or GB. If no units are specified, defaults to KB.

This specifies the amount of data that Opus will read or write at once when [copying files](/Manual/file_operations/copying_moving_and_deleting_files/README.md) using its own custom code. Although it shouldn't matter, some USB devices or networks appear to be sensitive to the size of the copy buffer. If you find that copies are much slower or less reliable than you would expect, try increasing or decreasing the buffer size.

The `Copy BUFSIZE` command can be used to override this setting on individual buttons, hotkeys, etc.

This buffer is in addition to any buffering provided by the filesystem, hardware, and so on; it is not connected to the non-buffered IO mode controlled by the **copy_nonbufferio_threshold** setting.

In the usual case where **copy_allow_delegation** is **True**, the **copy_buffer_size** and **copy_nonbufferio_threshold** settings have no effect on normal file-to-file copies, but can still affect special situations such as splitting/joining files, copying out of archives, and so on.
</td></tr><tr><td>

**copy_nonbufferio_threshold**</td><td>
</td><td>

File size threshold above which copies, done using the custom file-copying code, to or from local devices will be performed in non-buffered mode. Non-buffered mode bypasses filesystem buffers provided by Windows. Units can be KB, MB or GB. If no units are specified, defaults to MB.

For very large files, copying in non-buffered mode can increase the memory efficiency, copy speed and UI responsiveness. On the other hand, non-buffered mode may slow things down for smaller files or certain devices. In rare cases, non-buffered mode may not work at all (e.g. if you have a device which mis-reports its sector size).

Set the value to 0 (zero) to disable non-buffered mode. For compatibility reasons, it is disabled by default. If you wish to enable it, we recommend 1 MB as a good starting value.

The `Copy NONBUFIO` command can be used to override this setting on individual buttons, hotkeys, etc.

In the usual case where **copy_allow_delegation** is **True**, the **copy_buffer_size** and **copy_nonbufferio_threshold** settings have no effect on normal file-to-file copies, but can still affect special situations such as splitting/joining files, copying out of archives, and so on.
</td></tr><tr><td>

**dos_automap_unc_paths**</td><td>
</td><td>

Automatically create drive letter mappings for UNC paths in [MS-DOS batch commands](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.md). This lets you run DOS batch scripts on network drives directly from a UNC path.
</td></tr><tr><td>

**move_netshare_semantics**</td><td>
</td><td>

Special handling for PGP Netshare when moving folders. PGP Netshare behaves differently when folders are moved compared to files - turn this option on if you are finding that moving folders to Netshare-protected locations is failing.
</td></tr><tr><td>

**network_errors**</td><td>
Global</td><td>

Specify error codes that indicate network authentication errors. Some network filesystems return undocumented error codes in the case of a username/password authentication error - if you are finding that you simply get an error dialog when attempting to connect to a network drive, you should note the error code and add it to this option. When Opus receives that error code it will treat it as an authentication failure and prompt you for credentials to access the resource. You can specify multiple error codes by separating them with semi-colons (e.g. **50;1003;1245**).
</td></tr><tr><td>

**no_copy_dir_dates**</td><td>
</td><td>
Disable copying of folder timestamps. Timestamps will only be preserved for files when copying; folders that are created as part of a copy operation will have the current time and date.
</td></tr><tr><td>

**remember_net_paths**</td><td>
</td><td>

Opus normally remembers the previous path used in a system File Open or Save dialog (for example, when you use the [Preferences Backup or Restore](../../backing_up_and_restoring_preferences.md) function), but for performance reason it does not remember network paths. Turn this option on if you want Opus to remember network paths as well.
</td></tr><tr><td>

**size_on_disk_thorough**</td><td>
</td><td>

Off by default. If turned on, folder size calculations will be significantly slower, but Opus will display more accurate information in the "Size on Disk" column when esoteric NTFS compression modes are in use.

This does not affect sizes reported for things like Zip archives and other non-filesystem compression methods. Similarly, sizes reported for standard NTFS compression modes, such as you can turn on via a file's Properties dialog, are also not affected. The difference comes with unusual NTFS compression modes which can only be set via the Windows compact.exe command, such as /EXE:LZX. A bug in Windows means files compressed with those modes are incorrectly reported as uncompressed. There is no way to know that such compression modes are in use, and the only way to correctly report size-on-disk values for them is to do an additional query *for every file*. This extra query is extremely slow, especially on network drives, and the data is not cached by the operating system when a folder is re-read.

We recommend leaving this setting off unless you really need the more accurate information.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**Category: FTP**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
Option</td><td>

** Global? **</td><td>
Description
</td></tr><tr><td>

**ftp_copy_buffer_size**</td><td>
</td><td>
FTP copy buffer size (in bytes). This defines the size of the buffer used when transferring files via FTP. You should not normally need to change this.
</td></tr><tr><td>

**ftp_dblclk_cache_time**</td><td>
</td><td>

Time (in minutes) to cache double-clicked files from [FTP](/Manual/ftp/README.md) sites. When you double-click a file to open it on an FTP site, Opus downloads the file and saves it to a temporary folder. If you double-click the same file again within the specified time, the already-downloaded file will be used to save downloading the file again. This is set to 0 by default, meaning files are not automatically cached for double-click.
</td></tr><tr><td>

**ftp_do_not_cache**</td><td>
</td><td>

Normally the [FTP](/Manual/ftp/README.md) system caches the directory listings of remote sites to improve performance. Turn this option on if you want to force remote directories to be refreshed every time you change folder on an FTP site.
</td></tr><tr><td>

**ftp_no_case_sensitive**</td><td>
</td><td>

FTP sites are normally case sensitive (e.g. a file called *TEST.TXT* would be different from a file called *test.txt*). Set this option to disable case sensitivity for FTP sites.
</td></tr><tr><td>

**ftp_no_pasv_change**</td><td>
</td><td>
If Opus detects a non-routable address has been specified as the result of a passive (PASV) FTP connection, it will try to correct this to the site's routable address. If you turn this option on then Opus will attempt to use the non-routable address as specified, which will only be successful if the FTP server is on the same network as the client machine.
</td></tr><tr><td>

**ftp_ssl_verbose**</td><td>
</td><td>
Causes the FTP log to display extended output during SSL connections.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**Category: Image Formats**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
Option</td><td>

** Global? **</td><td>
Description
</td></tr><tr><td>

**amiga_icon_borders**</td><td>
</td><td>
Display borders around Amiga icons in thumbnails mode.
</td></tr><tr><td>

**amiga_icon_palette**</td><td>
</td><td>
Palette to use when displaying legacy Amiga icons.
</td></tr><tr><td>

**clipboard_image_paste**</td><td>
</td><td>

If you have an image in your clipboard (e.g. via the PrtScn key) and paste into a folder, Opus will save the clipboard image into a file. This setting changes the image format which will be used: JPG, PNG, BMP or GIF.

You can also set your <kbd>Ctrl+V</kbd> hotkey to run `Clipboard PASTE AS=ask` to have Opus prompt you for the image format (and filename) when you paste an image into a folder. In that case, this setting determines the format that is selected by default.
</td></tr><tr><td>

**clipboard_image_paste_dpi**</td><td>
</td><td>
When turned on, pasting clipboard image data to a file (by pressing <kbd>Ctrl+V</kbd> in a Lister) will automatically scale it to compensate for the system DPI.
</td></tr><tr><td>

**psd_image_preference**</td><td>
</td><td>
Photoshop PSD files can have up to three embedded images: A small (164x164) thumbnail with very lossy compression and no opacity/alpha data; a full-size, flattened preview image, stored in a lossless format, which can include opacity/alpha data; and finally the full, layered image data in Photoshop's internal format. (The layered data is not decoded by Opus, and few things other than Photoshop itself will render it.)

By default, Opus uses the small thumbnail image for thumbnails and the full-size preview image for the viewer. The setting allows you to override this so that one image or the other is used for both thumbnails and the viewer.

If you want Opus to show PSD thumbnails larger than 164x164, or with opacity/alpha data, select the option to use the preview image for both the viewer and thumbnails.

However, some PSD files do not have valid preview images, so there is also the option of never using the preview images and always using the small thumbnails, even in the viewer. Whether a PSD contains a flat preview image depends on how it was saved from Photoshop. The "maximize compatibility" or similar option should be turned on to include a preview image. In Photoshop CC 2015.5.0, the option is under Preferences / File Handling. In some cases, where there is no 'real' preview image there will be a black and white placeholder with text, written by Photoshop, telling you there is no preview image. Unfortunately, some versions of Photoshop write a corrupt placeholder image in some cases. (The data is well-formed, but the image it represents is not. In either case, it is difficult for Opus to detect if a 'real' preview image is there, or just a placeholder, as both are simply different pixel data encoded into exactly the same part of the file as a real preview image.) If your workflow cannot be changed and results in PSD files with missing or corrupt preview images, you can tell Opus to always use the small thumbnails, even in the viewer, so you can at least get a rough idea of what each file looks like.
</td></tr><tr><td>

**tiff_assume_alpha**</td><td>
</td><td>
Assume the 4th channel in TIFF images is (non-multiplied) alpha in files which do not specify its meaning. With this option turned off a 32-bit TIFF image must specify that it contains a valid alpha channel for Opus to treat it as so.
</td></tr><tr><td>

**tiff_max_doc_metadata**</td><td>
</td><td>
Maximum size (in megabytes) of TIFF images that Opus will attempt to extract document metadata from. This prevents problems with very large TIFFs, for example those saved by Photoshop.
</td></tr><tr><td>

**use_color_management**</td><td>
</td><td>
Use color management when loading images. If enabled Opus will check to see if an image file contains a color profile, and if so will use the ICC file you specify (or the default sRGB profile) it to render the image more accurately. Currently this is only used for JPEG and PNG images.
</td></tr><tr><td>

**viewer_disable_internal**</td><td>
</td><td>

Allows you to disable built-in image formats in the viewer and preview pane. Does not affect viewer plugins (which can already be disabled directly); in fact, the purpose is to allow you to override internal viewers with plugins and third-party components in situations where they cannot do so themselves (generally, Preview Handlers and ActiveX controls which don't know anything about Opus). For example, you may wish to divert the TIFF viewer to a third-party ActiveX control which handles multi-page TIFFs. The setting is a string listing the image types you wish to disable. Setting it to **tiff** would disable the internal TIFF viewer. Setting it to **JPG,PNG** would disable the internal JPG and PNG viewers.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**Category: Information Display**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
Option</td><td>

** Global? **</td><td>
Description
</td></tr><tr><td>

**custom_date_format**</td><td>
</td><td>

Opus normally uses the date format defined by the system (or the current locale) when displaying dates (e.g. in date columns in the Lister). This setting allows you to override it and specify your own custom format.

See the [Codes for date and time](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.md) page for information on date and time formats.
</td></tr><tr><td>

**custom_date_format_long**</td><td>
</td><td>

Similar to **custom_date_format** but used in places where a long (more verbose) date format is used. The long date format is not used in many places, so **custom_date_format** is more likely what you want if you are not sure.
</td></tr><tr><td>

**custom_time_format**</td><td>
</td><td>

Opus normally uses the time format defined by the system (or the current locale) when displaying times (e.g. in date/time columns in the Lister). This setting allows you to override it and specify your own custom format.

See the [Codes for date and time](/Manual/reference/command_reference/external_control_codes/codes_for_date_and_time.md) page for information on date and time formats.
</td></tr><tr><td>

**deffmt_cloud_availability**</td><td>
</td><td>

Prevents the **Availability** column being added to the **Cloud Storage** folder format automatically.

When you save a new default folder format and choose the option to replace all existing formats, a few formats get extra columns added automatically. In most cases these columns are important, but some can be overridden via options like this.
</td></tr><tr><td>

**deffmt_cloud_status**</td><td>
</td><td>

Prevents the **Status** (**Status Icons**) column being added to the **Cloud Storage** folder format automatically. (See **deffmt_cloud_availability**, above.)
</td></tr><tr><td>

**desc_show_info**</td><td>
</td><td>

For each file, the **Description** column normally shows:

- A metadata summary. (e.g. Picture type and dimensions, Audio codec and bitrate.)
- The user-defined description, if any. (This may be set via the **Properties, Description** command on the default toolbars. Some file types also allow user-defined descriptions/comments within their tags.)
- The target path, if the file is a shortcut or link. This option lets you remove the user-defined descriptions and/or targets from the Description column. For example, if you have added the separate **User description** and **Target** columns then you may want only the metadata summary to be left in the **Description** column.
</td></tr><tr><td>

**display_folder_extensions**</td><td>
</td><td>

If this option is enabled, folders are treated as having extensions (suffixes) for the purpose of display only (i.e. in the *Name* and *Extension* columns). For example, a folder named "Hello.World" would show "World" in the Extension column instead of showing nothing.
</td></tr><tr><td>

**file_size_units**</td><td>
</td><td>

Specifies the units to use when displaying file sizes and disk space. The traditional form is to use binary units (2^10-based) with "decimal" prefixes (1 KB = 1024 bytes). You can also choose to use decimal (10^3-based) units (1 KB = 1000 bytes) or binary units (1 KiB = 1024 bytes). See [this Wikipedia page](http://en.wikipedia.org/wiki/Binary_prefix) for more information.
</td></tr><tr><td>

**graphs_separate_files_dirs**</td><td>
</td><td>
Bar graphs that appear in the file display (relative size, relative age) are calculated separately for files and folders. If you turn this option off, they are calculated for all items.
</td></tr><tr><td>

**group_column_maxwidth**</td><td>
</td><td>

Specifies the maximum width of the *Group* column. When file display columns are set to auto-size, this option prevents the *Group* column from growing larger than the specified number of pixels.
</td></tr><tr><td>

**image_res_units**</td><td>
</td><td>

Units to use for columns relating to image resolution (*Resolution (X), Resolution (Y)*). If not set, each image file itself specifies the units, and so you may have a mix of inches and centimetres in any one directory - setting this option overrides the images and always displays consistent units.
</td></tr><tr><td>

**image_size_units**</td><td>
</td><td>

Units to use for columns relating to image size (*Physical Width, Physical Height, Physical Size*). If not set, each image file itself specifies the units, and so you may have a mix of inches and centimetres in any one directory - setting this option overrides the images and always displays consistent units.
</td></tr><tr><td>

**multipart_extensions**</td><td>
</td><td>

A "multipart file extension" is a file extension that consists of more than one part separated by dots. For example, in the Unix world **.tar.gz** files are quite common. In many cases (renaming, sorting, etc.) it makes sense to treat this whole string as the file extension, rather than simply **.gz** as is standard on Windows. Opus does this automatically for several archive formats, and the **multipart_extensions** option lets you add your own custom extension as well. Enter one extension per line.
</td></tr><tr><td>

**name_group_high_pri_chars**</td><td>
</td><td>

When [grouping](/Manual/basic_concepts/sorting_and_grouping/README.md) the file list by filename, files beginning with these characters will be put in a "high-priority" group at the top of the list. Normally files beginning with a non-alphabetical character or number will be placed in the *Unspecified* group, but you could use this option to, for example, place files beginning with **!** or **\#** in a separate group.
</td></tr><tr><td>

**show_sharing_overlays**</td><td>
</td><td>

Windows 7 removed the icon overlay (![](/Manual/images/media/sharing_overlay.png)) for shared folders, but many people like this feature and so Opus substitutes its own. If you would prefer not to see these overlays, turn this option off. This option will have no effect if overlays are turned off completely via the *Show shortcut arrows and other icon overlays* option on the [File Display Columns / Icons](/Manual/preferences/preferences_categories/file_display_columns/icons.md) Preferences page.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**Category: Limits**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
Option</td><td>

** Global? **</td><td>
Description
</td></tr><tr><td>

**context_menu_max_files**</td><td>
</td><td>

Because generating context menus for large numbers of files can take quite a while, Opus displays a confirmation message when you right-click with more than a defined number of files selected. The limit defaults to 1000 but you can change this or set it to **0** for no confirmation at all.
</td></tr><tr><td>

**everything_max_results**</td><td>
</td><td>
Sets a limit to the number of search results that an Everything search can return.
</td></tr><tr><td>

**long_operation_notify_time**</td><td>
</td><td>
If an operation that would block the UI thread takes longer than the specified time, Opus will show a notification dialog letting you cancel the operation.
</td></tr><tr><td>

**max_folder_thumb_time**</td><td>
</td><td>
Specifies the maximum time (in milliseconds) that Opus will spend when generating the thumbnail for a folder.
</td></tr><tr><td>

**max_md5_file_size**</td><td>
</td><td>

Specifies the maximum file size (in kilobytes) that Opus will calculate a hash for when the one of the checksum columns are displayed in a Lister. If a file is larger than this size its checksum can still be generated manually with the `GetSizes HASH` command.

**Special values:**

- **0** - Ignore file sizes and always automatically calculate file hashes.
- **1** - Ignore file sizes and never automatically calculate file hashes.

(The name of this setting is historical, it applies to all hashes - not just MD5.)
</td></tr><tr><td>

**max_thumbnail_mem_size**</td><td>
</td><td>
The maximum memory (in megabytes) per file display for in-memory thumbnails. Opus will discard out-of-view thumbnails to keep the memory usage for each file display's thumbnails below the specified size. If set to 0 there is no limit.
</td></tr><tr><td>

**max_thumbnail_size**</td><td>
</td><td>

The maximum pixel size (width and height) that Opus will generate thumbnails at. Larger thumbnails require more memory. This controls the maximum size thumbnail that be selected on the [Thumbnails](../file_display_modes/thumbnails_mode/README.md) page in Preferences, and also via the [Thumbnails Size](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/README.md) slider.
</td></tr><tr><td>

**suggestion_popup_lines**</td><td>
</td><td>
Configures how many lines are shown at once in popup suggestion lists.
</td></tr><tr><td>

**zip_dblclk_cache_time**</td><td>
</td><td>

Time (in minutes) to cache double-clicked files from within ZIP files. When you double-click a file to open it from a ZIP file, Opus extracts the file (and possibly others, subject to the Auto-extract options on the [Archive Options](../zip_and_other_archives/archive_options.md) Preferences page), and saves it to a temporary folder. If you double-click the same file again within the specified time, the already-extracted file will be used to save extracting the file again. This is set to 0 by default, meaning files are not automatically cached for double-click.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>

**Category: Troubleshooting**</th><th>
</th><th>

</th></tr></thead><tbody><tr><td>
Option</td><td>

** Global? **</td><td>
Description
</td></tr><tr><td>

**clipboard_change_delay**</td><td>
</td><td>
Delay (in milliseconds) before processing clipboard change events. You might want to increase this if certain software (e.g. Microsoft Office) has problems modifying the clipboard while Opus is running.
</td></tr><tr><td>

**collection_change_delay**</td><td>
</td><td>

Delay (in milliseconds) before processing external delete/rename operations in [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md). You might want to increase this if you find that files are disappearing from your file collections when you edit them in other programs (e.g. Word).
</td></tr><tr><td>

**context_menu_debug**</td><td>
</td><td>

Output debug information for context menu extensions. See the [FAQ](https://resource.dopus.com/t/crash-exit-or-high-cpu-when-right-clicking-certain-files/1335) on debugging context menu problems for more information. Users of Directory Opus Light can set the registry value **HKEY_CURRENT_USER\SOFTWARE\GPSoftware\Directory Opus\ContextMenuDebug** (DWORD) = 1 as an alternative to this option.
</td></tr><tr><td>

**crash_debug_button**</td><td>
</td><td>
When turned on, adds a "Debug" button to the Opus crash dialog, allowing you to invoke the normal Windows crash behavior. If a Just-In-Time debugger is installed, this will allow you to debug the process in its current state. This option should only be turned on if you are a developer working on a plugin or shell extension; it is not likely to be useful to anyone else.
</td></tr><tr><td>

**crash_handler**</td><td>
</td><td>

Opus includes a custom crash handler which aims to provide information about a crash that can be used by GP Software to track down the cause. It saves a log ("dump") of parts of the process memory, and you can use the built-in crash submitter tool in the Help menu to upload these automatically. The crash handler is partly managed by a separate process (dopusrt.exe), which Opus starts automatically (and will restart automatically, if it's killed).

If you don't want to use the crash handler for some reason (e.g. if it's causing troubles of its own), set this flag to **False**.
</td></tr><tr><td>

**crash_log_memory**</td><td>
</td><td>
When turned on, automatically generated crash logs (also known as "crash dumps") will include all memory within the process. This can make them more useful when diagnosing problems, but also greatly increases their file size and the chance they will include private data. You should not turn on this this setting unless asked to by technical support.
</td></tr><tr><td>

**debug_icon_data**</td><td>
</td><td>
You should not normally modify this setting. Technical support may ask you to enable it to help diagnose problems with icons generated by third party components.
</td></tr><tr><td>

**mixed_dpi_mitigations**</td><td>
</td><td>

Windows has a large number of bugs which are triggered by using multiple monitors with different DPIs (not just high-DPI monitors, but where there is more than one screen and they are not all set to the same scaling factor). Some of these Windows bugs can also be triggered by changing the DPI and not rebooting.

The **mixed_dpi_mitigations** setting controls certain workarounds which Opus uses to try to make Windows behave properly when using displays with multiple DPIs. Unfortunately, the mitigations themselves can cause problems on some machines, while solving them on others. If the mitigations are turned off, the main symptom of the Windows bug is pop-up menus and tooltips opening in the wrong place and being very large or small. When the mitigations are turned on, there is a very small performance hit and, if something goes wrong, the potential for the screen to flicker when pop-up menus or tooltips open, or other unexpected visual glitches.

When set to *Automatic*, Opus will detect if the system is in a mixed-DPI mode and turn on the mitigations when it is, while avoiding them when it is not.

This setting is only visible on Windows 8.1 and above; ealier OS versions did not support multiple monitors at different DPIs.
</td></tr><tr><td>

**mtp_enable**</td><td>
</td><td>
This option can be used to disable the internal support for MTP (portable) devices. When turned off, devices will be accessed by a hosted Windows Explorer view.
</td></tr><tr><td>

**no_external_change_notify**</td><td>
</td><td>

Don't monitor for external file changes. This lets you disable the detection of file changes that occur outside of Opus - only file operations that Opus itself performs will be noticed and reflected in the Lister.
</td></tr><tr><td>

**notify_debug**</td><td>
</td><td>

Output debug information for file notification. If you are having problems with Opus not noticing file changes that happen outside of Opus, tech support may ask you to turn this on to gather debugging information.

Turning this option on will reduce performance. Do not turn it on unless you are investigating a problem, and turn it off when you are done.

See the [FAQ](https://resource.dopus.com/t/changes-to-folders-are-not-being-detected/1786) for more information.
</td></tr><tr><td>

**notify_debug_exclude**</td><td>
</td><td>

A regular expression which filters the **notify_debug** output by path. If this regex is defined, a path will only be reported if it (or a substring) matches the regex.
</td></tr><tr><td>

**notify_debug_include**</td><td>
</td><td>

A regular expression which filters the **notify_debug** output by path. If this regex is defined, a path will only be reported if it (or a substring) does not match the regex.
</td></tr><tr><td>

**notify_max_time**</td><td>
Global</td><td>
The maximum amount of time, in milliseconds, each file display will spend processing change notifications from the filesystem before considering other inputs and events.

Defaults to 50 milliseconds. In rare situations, you may need to raise this from its default value if events are being generated faster than they are consumed. You can also specify 0 (zero) to process change events indefinitely, although you would probably only want to do so as a test, not as a permanent setting. If this is set to zero, or set too high, file displays could become less responsive to user input when a lot of filesystem events are being generated.

This is a global setting. If you change it for one user on a machine then it will affect all other users, as is most likely required. On a multi-user system, if the setting is changed by one user, the others will not see the change until they restart Opus.
</td></tr><tr><td>

**notify_min_items**</td><td>
Global</td><td>

The minimum number of events to process before checking the **notify_max_time** time limit. See the description of **notify_max_time**, above, for situations where you may wish to raise this, and how the setting behaves for multiple users.
</td></tr><tr><td>

**script_output_level**</td><td>
</td><td>

Lets you adjust the type of diagnostic output shown in the *Script Log* (*[Utility Panel](/Manual/basic_concepts/the_lister/utility_panel.md) / Other Logs*).

This affects diagnostics that come from Opus itself and plugin DLLs. Output sent to the log from scripts calling the **DOpus.Output** method is always shown.
</td></tr><tr><td>

**script_output_throttle**</td><td>
</td><td>

When on, diagnostic output shown in the *Script Log* (*[Utility Panel](/Manual/basic_concepts/the_lister/utility_panel.md) / Other Logs*) will suppress identical messages which repeat too frequently.

This should normally be left on to prevent performance issues if a diagnostic message is triggered too often. Turning it off can be useful if you are working on a plugin DLL and need to log repetitive events without any of them being dropped.

This affects diagnostics that come from Opus itself and plugin DLLs. Output sent to the log from scripts calling the **DOpus.Output** method is always shown.
</td></tr><tr><td>

**shellchange_debug**</td><td>
</td><td>

Output debug information for shell file notification. If you are having problems with Opus not noticing file or folder changes that happen outside of Opus, tech support may ask you to turn this on to gather debugging information. See the [FAQ](https://resource.dopus.com/t/changes-to-folders-are-not-being-detected/1786) for more information.
</td></tr><tr><td>

**sync_debug**</td><td>
</td><td>

This should normally be left off, but you may be asked to turn it on to debug decisions made by the [Synchronize tool](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.md). If you use the Synchronize tool while this option is on, a file with debugging information will be created on your desktop.
</td></tr><tr><td>

**thumbnail_debug**</td><td>
</td><td>
Output debug information for thumbnail generation. Tech support may ask you to turn this on to gather debugging information. Reduces performance and should be turned off when not needed.
</td></tr></tbody>
</table>

