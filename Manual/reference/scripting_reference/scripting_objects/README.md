# Scripting Objects

Scripts can interact with Opus using a number of different objects. For example, the **Lister** object represents a physical [Lister](/Manual/basic_concepts/the_lister/README.md) window, providing information about that Lister to the script and letting the script modify or control that Lister.

An object has two main types of interface that you can call on:

- *Properties* let the script query (and sometimes set) a simple value. For example, the **Lister** object has a **title** property that lets the script retrieve the Lister window's title string.
- *Methods* are functions an object provides that the script can invoke to perform a task. For example, the **DOpus** object has an **Output** method that lets the script output a text string to the script log.

The main distinction between properties and methods is that methods can (but don't always) accept arguments that modify their behavior, and don't have to (but often do) return a result.

#### Variable types

Properties and methods that return a result can return a number of different types of variables, and methods often take one or more parameters that can also be a number of types. ActiveX scripting languages are generally *typeless* - that is, a variable's type does not have to be defined in advance, and conversion from one type to another is often (but not always) automatic. Opus scripting mainly uses variables of the following types:

- *Int* - a whole number (signed; valid range is -2147483648 to 2147483647).
- *Currency* - this is a standard variant type, and is used by Opus in just a couple of cases that require numbers larger than an *Int* can hold (unfortunately ActiveX scripting does not always support a 64 bit integer type).
- *Decimal* - an unsigned 64 bit value (maximum value 18,446,744,073,709,551,616). Not all languages support this - JScript does, but VBScript does not.
- *String* - a text string
- *Bool* - a Boolean (either **True** or **False**)
- *Date* - a date/time value
- *Collection* - a collection of multiple objects of (generally) the same type. Collections can be easy enumerated in some languages (e.g. in VBScript, using the *For Each* construct). Collections are only returned by Opus - unlike an array (or a Vector object), they are never created or modified directly (although some script methods can be used to modify them in certain cases). For example, the **Tab** object has a property called **selected** that represents all currently selected items in that tab - it is a *collection* of items.
- *Object* - an Opus script object with defined methods and properties (one of the object types listed below). Some objects can be both an object and a collection - that is, they have methods and properties, but can also be enumerated like a collection. Some objects also have a *default value* - that is, simply using the object's name without any method or property will return a value of its own. For example, the **Metadata** object's default value is a string indicating the primary type of metadata available. You can also refer to an object's default value using the special **def_value** property name.
- *Variant* - a variable of any type (this is used with a few objects - for example, a **Var** object can store a variant)

#### Global objects

There are two objects that are provided to scripts as global variables when they are invoked by Opus:

- **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.md)**: This** **object is available to *all* scripts. It provides various helper methods, and collections that let you access things like Listers and toolbars.
- **[Script](/Manual/reference/scripting_reference/scripting_objects/script.md)**: This** **object is provided to [script add-ins](/Manual/scripting/script_add-ins/README.md) when their various event handlers are invoked. It provides information relating to the script itself.

#### Event objects

There are a number of objects that Opus provides as parameters to methods within a script. For example, when a [script function](/Manual/scripting/script_functions.md) is invoked (e.g. when the button is clicked), Opus calls its **OnClick** method, passing it a **ClickData** object.

- **[AboutData](/Manual/reference/scripting_reference/scripting_objects/aboutdata.md)**: This object is provided to the **[OnAboutScript](scripting_events/onaboutscript.md)** method, which is called when the user clicks the *About* button for a script in the **[Script Management](/Manual/scripting/script_management/README.md)** dialog.
- **[ActivateListerData](/Manual/reference/scripting_reference/scripting_objects/activatelisterdata.md)**: This object is provided to the **[OnActivateLister](scripting_events/onactivatelister.md)** method, which is called whenever a Lister window is activated or deactivated.
- **[ActivateTabData](/Manual/reference/scripting_reference/scripting_objects/activatetabdata.md)**: This object is provided to the **[OnActivateTab](scripting_events/onactivatetab.md)** method, which is called whenever a tab is activated.
- **[AddCmdData](/Manual/reference/scripting_reference/scripting_objects/addcmddata.md)**: This object is provided to the **[OnAddCommands](scripting_events/onaddcommands.md)** method, which allows a script to [add new internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md).
- **[AddColData](/Manual/reference/scripting_reference/scripting_objects/addcoldata.md)**: This object is provided to the **[OnAddColumns](scripting_events/onaddcolumns.md)** method, which allows a script to [add new information columns](/Manual/scripting/example_scripts/adding_a_new_column.md).
- **[AfterFolderChangeData](/Manual/reference/scripting_reference/scripting_objects/afterfolderchangedata.md)**: This object is provided to the **[OnAfterFolderChange](scripting_events/onafterfolderchange.md)** method, which is called after a new folder has been read.
- **[BeforeFolderChangeData](/Manual/reference/scripting_reference/scripting_objects/beforefolderchangedata.md)**: This object is provided to the **[OnBeforeFolderChange](scripting_events/onbeforefolderchange.md)** method, which is called before a new folder is read.
- **[ClickData](/Manual/reference/scripting_reference/scripting_objects/clickdata.md)**: This object is provided to the **[OnClick](scripting_events/onclick.md)** method, which is called whenever a [script function](/Manual/scripting/script_functions.md) is invoked (e.g. when the button is clicked or hotkey pressed).
- **[CloseListerData](/Manual/reference/scripting_reference/scripting_objects/closelisterdata.md)**: This object is provided to the **[OnCloseLister](scripting_events/oncloselister.md)** method, which is called before a Lister closes.
- **[CloseTabData](/Manual/reference/scripting_reference/scripting_objects/closetabdata.md)**: This object is provided to the **[OnCloseTab](scripting_events/onclosetab.md)** method, which is called before a tab closes.
- **[ConfigChangeData](/Manual/reference/scripting_reference/scripting_objects/configchangedata.md)**: This object is provided to the **[OnScriptConfigChange](scripting_events/onscriptconfigchange.md)** method, which notifies a script when the user edits the script's configuration.
- **[DisplayModeChangeData](/Manual/reference/scripting_reference/scripting_objects/displaymodechangedata.md)**: This object is provided to the **[OnDisplayModeChange](scripting_events/ondisplaymodechange.md)** method, which is called when the display mode changes in a tab.
- **[DoubleClickData](/Manual/reference/scripting_reference/scripting_objects/doubleclickdata.md)**: This object is provided to the **[OnDoubleClick](scripting_events/ondoubleclick.md)** method, which is called when a file or folder is double-clicked.
- **[FileOperationCompleteData](/Manual/reference/scripting_reference/scripting_objects/fileoperationcompletedata.md)**: This object is provided to the **[OnFileOperationComplete](scripting_events/onfileoperationcomplete.md)** method, which lets you receive notification when certain file operations complete.
- **[FilesystemChangeData](/Manual/reference/scripting_reference/scripting_objects/filesystemchangedata.md)**: This object is provided to the **[OnFilesystemChange](scripting_events/onfilesystemchange.md)** method, after you've established monitoring for file or folder changes via the **[FSUtil](/Manual/reference/scripting_reference/scripting_objects/fsutil.md).WatchChanges** method.
- **[FlatViewChangeData](/Manual/reference/scripting_reference/scripting_objects/flatviewchangedata.md)**: This object is provided to the **[OnFlatViewChange](scripting_events/onflatviewchange.md)** method, which is called when the Flat View mode changes in a tab.
- **[GetCopyQueueNameData](/Manual/reference/scripting_reference/scripting_objects/getcopyqueuenamedata.md)**: This object is provided to the **[OnGetCopyQueueName](scripting_events/ongetcopyqueuename.md)** event, which is called whenever a copy operation begins that uses automatically-managed copy queues.
- **[GetCustomFieldData](/Manual/reference/scripting_reference/scripting_objects/getcustomfielddata.md)**: This object is provided to the **[OnGetCustomFields](scripting_events/ongetcustomfields.md)**event, which lets a [rename script](/Manual/scripting/rename_scripts/README.md) add its own fields to the *Rename* dialog.
- **[GetNewNameData](/Manual/reference/scripting_reference/scripting_objects/getnewnamedata.md)**: This object is provided to the **[OnGetNewName](scripting_events/ongetnewname.md)** method, which is one of the supported methods a [rename script](/Manual/scripting/rename_scripts/README.md) can provide.
- **[ListerResizeData](/Manual/reference/scripting_reference/scripting_objects/listerresizedata.md)**: This object is provided to the **[OnListerResize](scripting_events/onlisterresize.md)** event, which is called whenever a Lister window is resized.
- **[ListerUIChangeData](/Manual/reference/scripting_reference/scripting_objects/listeruichangedata.md)**: This object is provided to the **[OnListerUIChange](scripting_events/onlisteruichange.md)** method, which is called when various user interface elements (tree, viewer, etc) are open or closed in a Lister.
- **[OpenListerData](/Manual/reference/scripting_reference/scripting_objects/openlisterdata.md)**: This object is provided to the **[OnOpenLister](scripting_events/onopenlister.md)** method, which is called when a new Lister is opened.
- **[OpenTabData](/Manual/reference/scripting_reference/scripting_objects/opentabdata.md)**: This object is provided to the **[OnOpenTab](scripting_events/onopentab.md)** method, which is called when a new tab is opened.
- **[ScriptColumnData](/Manual/reference/scripting_reference/scripting_objects/scriptcolumndata.md)**: This object is provided to the [script-specified method](/Manual/scripting/example_scripts/adding_a_new_column.md) used to add new columns to Opus.
- **[ScriptCommandData](/Manual/reference/scripting_reference/scripting_objects/scriptcommanddata.md)**: This object is provided to the [script-specified method](scripting_events/onscriptcommand.md) used to [add new internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) to Opus.
- **[ScriptFAYTCommandData](/Manual/reference/scripting_reference/scripting_objects/scriptfaytcommanddata.md)**: This object is provided to the [script-specified method](scripting_events/onscriptcommand.md) used to [extend the FAYT field](/Manual/scripting/example_scripts/extending_the_fayt.md).
- **[ScriptInitData](/Manual/reference/scripting_reference/scripting_objects/scriptinitdata.md)**: This object is provided to the **[OnInit](scripting_events/oninit.md)** method, which is called once to initialize each script in the *Script Addins* folder.
- **[ShutdownData](/Manual/reference/scripting_reference/scripting_objects/shutdowndata.md)**: This object is provided to the **[OnShutdown](scripting_events/onshutdown.md)** method, which is called before Opus shuts down.
- **[SourceDestData](/Manual/reference/scripting_reference/scripting_objects/sourcedestdata.md)**: This object is provided to the **[OnSourceDestChange](scripting_events/onsourcedestchange.md)** method, which is called when the source or destination state of a tab changes.
- **[StartupData](/Manual/reference/scripting_reference/scripting_objects/startupdata.md)**: This object is provided to the **[OnStartup](scripting_events/onstartup.md)** method, which is called when Opus starts up.
- **[StyleSelectedData](/Manual/reference/scripting_reference/scripting_objects/styleselecteddata.md)**: This object is provided to the **[OnStyleSelected](scripting_events/onstyleselected.md)** method, which is called when a new [style](/Manual/basic_concepts/the_lister/styles.md) is chosen in a Lister.
- **[SystemSettingChangeData](/Manual/reference/scripting_reference/scripting_objects/systemsettingchangedata.md)**: This object is provided to the **[OnSystemSettingChange](scripting_events/onsystemsettingchange.md)** method, which is called when various system settings change.
- **[TabClickData](/Manual/reference/scripting_reference/scripting_objects/tabclickdata.md)**: This object is provided to the **[OnTabClick](scripting_events/ontabclick.md)** event, which is called whenever a tab is clicked with a qualifier key held down.
- **[ViewerEventData](/Manual/reference/scripting_reference/scripting_objects/viewereventdata.md)**: This object is provided to the **[OnViewerEvent](scripting_events/onviewerevent.md)** event, which is called whenever certain events occur in a standalone [image viewer](/Manual/additional_functionality/viewing_images/README.md).

#### Other objects

The remaining objects are all obtained using methods or properties provided by the objects listed above. For example, a **Lister** object is obtained using the **DOpus.listers** collection property, and a **Vector** object is obtained using the **DOpusFactory.Vector** method.

- **[Alias](/Manual/reference/scripting_reference/scripting_objects/alias.md)**: This object represents a [folder alias](/Manual/basic_concepts/the_lister/navigation/aliases.md), and is retrieved using the **Aliases** object.
- **[Aliases](/Manual/reference/scripting_reference/scripting_objects/aliases.md)**: This object is a collection of all defined folder aliases. It is retrieved using the **DOpus.aliases** collection property.
- **[Args](/Manual/reference/scripting_reference/scripting_objects/args.md)**: This object represents the arguments supplied on the command line for [script-defined internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md). It is retrieved from the **ScriptCommandData.Func.args** property.
- **[AudioMeta](/Manual/reference/scripting_reference/scripting_objects/audiometa.md)**: This object provides metadata properties relating to audio files. It is obtained from the **Metadata** object.
- **[AudioCoverArt](/Manual/reference/scripting_reference/scripting_objects/audiocoverart.md)**: This object provides access to an audio file's embedded cover art. It is obtained from the **AudioMeta.coverart** property.
- **[Blob](/Manual/reference/scripting_reference/scripting_objects/blob.md)**: This object provides a simple interface for dealing with binary data. It is obtained from the **DOpusFactory.Blob** method and also returned by the **AudioCoverArt.data** property.
- **[BusyIndicator](/Manual/reference/scripting_reference/scripting_objects/busyindicator.md)**: A **BusyIndicator** object lets you control the breadcrumbs bar busy indicator from your script.
- **[Column](/Manual/reference/scripting_reference/scripting_objects/column.md)**: This object represents a column that has been added to the display in a tab. A collection of columns can be obtained from the **Format** object.
- **[Command](/Manual/reference/scripting_reference/scripting_objects/command.md)**: This object is used to run Opus commands. It is obtained from the **ScriptCommandData.func** or **ClickData.func** properties, and can also be created by the **DOpusFactory.Command** method.
- **[Control](/Manual/reference/scripting_reference/scripting_objects/control.md)**: The **Control** object represents a control on a [script dialog](/Manual/scripting/script_dialogs/README.md); it lets you read and modify a control's value (and contents).
- **[CustomFieldData](/Manual/reference/scripting_reference/scripting_objects/customfielddata.md)**: The **CustomFieldData** object is provided to a [rename script](/Manual/scripting/rename_scripts/README.md) via the **[GetNewNameData](/Manual/reference/scripting_reference/scripting_objects/getnewnamedata.md).custom** property. It provides access to the value of any [custom fields](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.md) that your script added to the *Rename* dialog.
- **[Date](/Manual/reference/scripting_reference/scripting_objects/date.md)**: This object is provided to make it easier to deal with variables representing dates. It is obtained from the **DOpusFactory.Date** method as well as various properties in other objects.
- **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md)**: This object is used to display dialogs or popup menus. It is obtained from the **Func.Dlg**, **Command.Dlg** or **DOpus.Dlg** methods.
- **[DialogListColumn](/Manual/reference/scripting_reference/scripting_objects/dialoglistcolumn.md)**: The **DialogListColumn** object represents a column in a *Details* mode *list view* control in a [script dialog.](/Manual/scripting/script_dialogs/README.md) It's obtained by enumerating the **[DialogListColumns](/Manual/reference/scripting_reference/scripting_objects/dialoglistcolumns.md)** object.**~control**
- **[DialogListColumns](/Manual/reference/scripting_reference/scripting_objects/dialoglistcolumns.md)**: The **DialogListColumns** object lets you query or modify the columns in a *Details* mode *list view* control in a [script dialog.](/Manual/scripting/script_dialogs/README.md) Use the **[Control](/Manual/reference/scripting_reference/scripting_objects/control.md).columns** property to obtain a **DialogListColumns** object.
- **[DialogListGroup](/Manual/reference/scripting_reference/scripting_objects/dialoglistgroup.md)**: The **DialogListGroup** object represents a group in a *list view* control in a [script dialog](/Manual/scripting/script_dialogs/README.md). It's returned by the **[Control](/Manual/reference/scripting_reference/scripting_objects/control.md).GetGroupById** method.
- **[DialogListItem](/Manual/reference/scripting_reference/scripting_objects/dialoglistitem.md)**: The **DialogListItem** object represents an item in a *combo box* or *list box* control in a [script dialog](/Manual/scripting/script_dialogs/README.md). It's returned by the **[Control](/Manual/reference/scripting_reference/scripting_objects/control.md).GetItemAt** and **[Control](/Manual/reference/scripting_reference/scripting_objects/control.md).GetItemByName** methods.
- **[DialogOption](/Manual/reference/scripting_reference/scripting_objects/dialogoption.md)**: This object is used in conjunction with the **Dialog** object. It lets you specify a checkbox option that is added to the dialog.
- **[Dock](/Manual/reference/scripting_reference/scripting_objects/dock.md)**: This object represents a floating toolbar. The Toolbar object provides a collection that represents all instances of that toolbar that are currently floating.
- **[DocMeta](/Manual/reference/scripting_reference/scripting_objects/docmeta.md)**: This object provides metadata properties relating to document files. It is obtained from the **Metadata** object.
- **[DOpusFactory](/Manual/reference/scripting_reference/scripting_objects/dopusfactory.md)**: This object is a helper object that you can use to create various other objects like **Map** and **Vector**. It is obtained from the **DOpus.Create** method.
- **[DPI](/Manual/reference/scripting_reference/scripting_objects/dpi.md)**: The **DPI** object is a helper object that provides a number of methods and properties relating to the system DPI setting. It's returned via the **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.md).DPI** property.
- **[Drive](/Manual/reference/scripting_reference/scripting_objects/drive.md)**: The **Drive** object provides information about a drive (hard drive, CD ROM, etc) on your system. A **Vector** of drives on your system can be obtained from the **[FSUtil](/Manual/reference/scripting_reference/scripting_objects/fsutil.md).Drives** method.
- **[ExeMeta](/Manual/reference/scripting_reference/scripting_objects/exemeta.md)**: This object provides metadata properties relating to executable (program) files. It is obtained from the **Metadata** object.
- **[Favorite](/Manual/reference/scripting_reference/scripting_objects/favorite.md)**: The **Favorite** object represents a [favorite folder](/Manual/basic_concepts/the_lister/navigation/favorites.md). It is retrieved by enumerating or indexing the [Favorites](/Manual/reference/scripting_reference/scripting_objects/favorites.md)object.
- **[Favorites](/Manual/reference/scripting_reference/scripting_objects/favorites.md)**: The **Favorites** object holds a collection of all the defined [favorite folders](/Manual/basic_concepts/the_lister/navigation/favorites.md). It is retrieved from the **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.md).favorites** method.
- **[File](/Manual/reference/scripting_reference/scripting_objects/file.md)**: This object lets you read or write binary data from or to a file. It is obtained from the **FSUtil.OpenFile** and **Item.Open** methods.
- **[FileAttr](/Manual/reference/scripting_reference/scripting_objects/fileattr.md)**: This object represents file attributes (like read only, archived, etc). It used by the **Item** and **Format** objects, and can be created by the **[FSUtil](/Manual/reference/scripting_reference/scripting_objects/fsutil.md).NewFileAttr** method.
- **[FileGroup](/Manual/reference/scripting_reference/scripting_objects/filegroup.md)**: This object exposes information about a file group (when a **Tab** is set to group by a particular column). It is used by the **Item** and **Tab** objects.
- **[FileSize](/Manual/reference/scripting_reference/scripting_objects/filesize.md)**: This object is used to represent a size in bytes (mainly because ActiveX scripting doesn't have proper support for 64 bit integers). It is used by the **Item** and **TabStats** objects.
- **[FiletypeGroup](/Manual/reference/scripting_reference/scripting_objects/filetypegroup.md)**: This object represents a file type group (as configured in the [File Type Groups](/Manual/file_types/file_type_groups.md) section of the [file type editor](/Manual/file_types/README.md)).
- **[FiletypeGroups](/Manual/reference/scripting_reference/scripting_objects/filetypegroups.md)**: This object represents a collection of one or more file type groups.
- **[Filter](/Manual/reference/scripting_reference/scripting_objects/filter.md)**: Lets you create a complex filter that can be used with commands like **Copy** when run from a script.
- **[FilterParseError](/Manual/reference/scripting_reference/scripting_objects/filterparseerror.md)**: Used to access information about a parsing error when working with **Filter** objects.
- **[FolderEnum](/Manual/reference/scripting_reference/scripting_objects/folderenum.md)**: This object lets a script enumerate the contents of a folder. It is obtained using the **FSUtil.ReadDir** method.
- **[FontMeta](/Manual/reference/scripting_reference/scripting_objects/fontmeta.md)**: This object provides metadata properties relating to font files. It is obtained from the **Metadata** object.
- **[Format](/Manual/reference/scripting_reference/scripting_objects/format.md)**: This object provides information about the display format in a tab. It is obtained from the **Tab.format** property.
- **[FSUtil](/Manual/reference/scripting_reference/scripting_objects/fsutil.md)**: This object provides various utility methods relating to file system activity. It is obtained from the **DOpus.FSUtil** property.
- **[Func](/Manual/reference/scripting_reference/scripting_objects/func.md)**: This object is passed to a [script function](/Manual/scripting/script_functions.md) (via **ClickData.func**) or [script-defined internal command](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) (via **ScriptCommandData.func**). It provides information relating to the function invocation (source and destination tabs, arguments, etc).
- **[GlobalFilters](/Manual/reference/scripting_reference/scripting_objects/globalfilters.md)**: This object lets you access information about the global filter settings (configured on the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences).
- **[Image](/Manual/reference/scripting_reference/scripting_objects/image.md)**: This object represents an image file or icon loaded from disk that can be displayed in a [script dialog](/Manual/scripting/script_dialogs/README.md).
- **[ImageMeta](/Manual/reference/scripting_reference/scripting_objects/imagemeta.md)**: This object provides metadata properties relating to image files. It is obtained from the **Metadata** object.
- **[IncludeFileInitData](/Manual/reference/scripting_reference/scripting_objects/includefileinitdata.md)**: If an [include file](/Manual/scripting/script_add-ins/include_files.md) script implements the optional **[oninitincludefile](scripting_events/oninitincludefile.md)** method, it receives this object to let it provide information about the include file.
- **[Item](/Manual/reference/scripting_reference/scripting_objects/item.md)**: This object represents a file or a folder. It can be returned from various methods of the **Tab** object, when enumerating a folder using the **FSUtil.ReadDir** method, and is used to provide files for a command to act on using the **Command** object.
- **[Items](/Manual/reference/scripting_reference/scripting_objects/items.md)**: The **Items** object lets you enumerate a list of one or more **Item** objects.
- **[Lister](/Manual/reference/scripting_reference/scripting_objects/lister.md)**: This object represents a [Lister](/Manual/basic_concepts/the_lister/README.md) window.
- **[Listers](/Manual/reference/scripting_reference/scripting_objects/listers.md)**: The **[Listers](/Manual/reference/scripting_reference/scripting_objects/listers.md)**object is a collection of all currently open Lister windows (each one represented by a **[Lister](/Manual/reference/scripting_reference/scripting_objects/lister.md)**object). It can be obtained from the **DOpus.listers** property.
- **[Map](/Manual/reference/scripting_reference/scripting_objects/map.md)**: This object is similar to an array or vector (e.g. **[Vector](/Manual/reference/scripting_reference/scripting_objects/vector.md)**) in that it can store one or more objects, but has the advantage of using a dictionary system to locate objects rather than numeric indexes. It is obtained from the **DOpusFactory.Map** method.
- **[Metadata](/Manual/reference/scripting_reference/scripting_objects/metadata.md)**: This object represents a file or folder's metadata. It can be obtained from the **Item.metadata** property, as well as the **FSUtil.GetMetadata** method.
- **[Msg](/Manual/reference/scripting_reference/scripting_objects/msg.md)**: The **Msg** object represents a [script dialog](/Manual/scripting/script_dialogs/README.md) input event message. It’s returned by the **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md).GetMsg** method which you call when running the message loop for a [detached dialog](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.md).
- **[OtherMeta](/Manual/reference/scripting_reference/scripting_objects/othermeta.md)**: This object provides general metadata properties relating to files and folders. It is obtained from the **Metadata** object.
- **[PairedFolder](/Manual/reference/scripting_reference/scripting_objects/pairedfolder.md)**: This object represents a [paired folder](/Manual/preferences/preferences_categories/frequently_used_paths/paired_folders.md) retrieved from the **FSUtil.GetFolderPair** method.
- **[Path](/Manual/reference/scripting_reference/scripting_objects/path.md)**: This object represents a file system path. It contains several methods to manipulate the path. Path objects are returned by several properties and can be created by the **FSUtil.NewPath** method.
- **[Progress](/Manual/reference/scripting_reference/scripting_objects/progress.md)**: This object represents a progress dialog, that lets you visually indicate to the user the progress of your script function. It is obtained from the **Command.progress** property.
- **[QuickFilter](/Manual/reference/scripting_reference/scripting_objects/quickfilter.md)**: This object provides information about the state of the quick filter in a tab. It's obtained from the **[Tab](/Manual/reference/scripting_reference/scripting_objects/tab.md).quickfilter** property.
- **[Rect](/Manual/reference/scripting_reference/scripting_objects/rect.md)**: The **Rect** object represents a rectangle.
- **[Results](/Manual/reference/scripting_reference/scripting_objects/results.md)**: This object represents the results of a command (the error code in the case of failure, plus any new tabs or Listers created by the command). It is obtained from the **Command.results** property.
- **[ScriptColorPair](/Manual/reference/scripting_reference/scripting_objects/scriptcolorpair.md)**: This object bundles a pair of colors (text / background) together.
- **[ScriptColumn](/Manual/reference/scripting_reference/scripting_objects/scriptcolumn.md)**: This object represents a [script-defined column](/Manual/scripting/example_scripts/adding_a_new_column.md). It is obtained from the **ScriptInitData.AddColumn** method, while processing the **OnInit** event.
- **[ScriptCommand](/Manual/reference/scripting_reference/scripting_objects/scriptcommand.md)**: This object represents a [script-defined internal command](/Manual/scripting/example_scripts/adding_a_new_internal_command.md). It is obtained from the **ScriptInitData.AddCommand** method, while processing the **OnInit** event.
- **[ScriptFAYTCommand](/Manual/reference/scripting_reference/scripting_objects/scriptfaytcommand.md)**: This object is provided as a property of the **ScriptCommand** object for script add-ins that [extend the FAYT field](/Manual/scripting/example_scripts/extending_the_fayt.md).
- **[ScriptConfig](/Manual/reference/scripting_reference/scripting_objects/scriptconfig.md)**: This object represents script-defined configuration data that Opus stores for each script. The configuration items are initialised via the **ScriptInitData.config** property, and are then available to the script via the **Script.config** property.
- **[ScriptStrings](/Manual/reference/scripting_reference/scripting_objects/scriptstrings.md)**: The **ScriptStrings** object is returned by the **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.md).strings** property. It lets you access any strings defined via [string resources](/Manual/scripting/resources/string_resources.md).
- **[ShellProperty](/Manual/reference/scripting_reference/scripting_objects/shellproperty.md)**: The **ShellProperty** object represents a shell property - an item of metadata for a file or folder that comes from Windows or third-party extensions. The **[FSUtil](/Manual/reference/scripting_reference/scripting_objects/fsutil.md).GetShellPropertyList** method lets you retrieve a list of available shell properties.
- **[SmartFavorite](/Manual/reference/scripting_reference/scripting_objects/smartfavorite.md)**: A **SmartFavorite** object represents an entry for a folder in the [SmartFavorites](/Manual/basic_concepts/the_lister/navigation/smartfavorites.md) table. It is retrieved by enumerating or indexing the **[SmartFavorites](/Manual/reference/scripting_reference/scripting_objects/smartfavorites.md)** object.
- **[SmartFavorites](/Manual/reference/scripting_reference/scripting_objects/smartfavorites.md)**: The **SmartFavorites** object lets you query the contents of the [SmartFavorites](/Manual/basic_concepts/the_lister/navigation/smartfavorites.md) table. It is retrieved from the **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.md).smartfavorites** property.
- **[SortOrder](/Manual/reference/scripting_reference/scripting_objects/sortorder.md)**: The **SortOrder** object is returned by the **[Format](/Manual/reference/scripting_reference/scripting_objects/format.md).manual_sort_order** property if [manual sort mode](/Manual/basic_concepts/sorting_and_grouping/manual_sorting.md) is active. It lets you query and modify the sort order.
- **[StringTools](/Manual/reference/scripting_reference/scripting_objects/stringtools.md)**: This object provides utility functions for string encoding and decoding. It is obtained from the **DOpusFactory.StringTools** method.
- **[StringSet](/Manual/reference/scripting_reference/scripting_objects/stringset.md)**: This object is similar to an array or vector (e.g. **[Vector](/Manual/reference/scripting_reference/scripting_objects/vector.md)**) of strings, but has the advantage of using a dictionary system to locate strings rather than numeric indexes. It is obtained from the **DOpusFactory.StringSet** and **StringSetI** methods.
- **[SysInfo](/Manual/reference/scripting_reference/scripting_objects/sysinfo.md)**: The **SysInfo** object is created by the **DOpusFactory.SysInfo** method. It lets scripts access miscellaneous system information that may not be otherwise easy to obtain from a script.
- **[Tab](/Manual/reference/scripting_reference/scripting_objects/tab.md)**: This object represents a folder tab in a Lister. A Lister's tabs are available via various Lister object properties (e.g. **Lister.activetab**) and also used to specify the source/destination of a command (e.g. **Command.sourcetab**).
- **[TabGroup](/Manual/reference/scripting_reference/scripting_objects/tabgroup.md)**: This object represents a [folder tab group](/Manual/basic_concepts/the_lister/tabs/tab_groups.md). It's accessed by enumerating the **[TabGroups](/Manual/reference/scripting_reference/scripting_objects/tabgroups.md)**object.
- **[TabGroups](/Manual/reference/scripting_reference/scripting_objects/tabgroups.md)**: This object provides access to and lets you modify the configured list of [folder tab groups](/Manual/basic_concepts/the_lister/tabs/tab_groups.md). It's obtained from the **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.md).tabgroups** property.
- **[TabGroupTabEntry](/Manual/reference/scripting_reference/scripting_objects/tabgrouptabentry.md)**: This object represents a folder tab in a [tab group.](/Manual/basic_concepts/the_lister/tabs/tab_groups.md)
- **[TabGroupTabList](/Manual/reference/scripting_reference/scripting_objects/tabgrouptablist.md)**: This object represents a list of folder tabs in a [tab group](/Manual/basic_concepts/the_lister/tabs/tab_groups.md).
- **[TabStats](/Manual/reference/scripting_reference/scripting_objects/tabstats.md)**: This object provides various statistics about a folder tab (the number of selected files, total number of items, etc). It is obtained from the **Tab.stats** and **Tab.selstats** properties.
- **[Toolbar](/Manual/reference/scripting_reference/scripting_objects/toolbar.md)**: This object represents a toolbar. It is obtained with the **DOpus.toolbars** and **Lister.toolbars** properties.
- **[Toolbars](/Manual/reference/scripting_reference/scripting_objects/toolbars.md)**: The **Toolbars** object lets you enumerate all the defined toolbars in your Directory Opus configuration (whether currently turned on or not).
- **[UnorderedSet](/Manual/reference/scripting_reference/scripting_objects/unorderedset.md)**: Similar to a **[StringSet](/Manual/reference/scripting_reference/scripting_objects/stringset.md)**but can store elements of any type rather than just strings.
- **[Var](/Manual/reference/scripting_reference/scripting_objects/var.md)**: This object represents a variable. Toolbar buttons, hotkeys and scripts can read and store variables, and variables can be saved from one session of Opus to another. The **Var** object is obtained from the **Vars** collection.
- **[Vars](/Manual/reference/scripting_reference/scripting_objects/vars.md)**: This object represents a collection of variables. Depending on the variables' scope it can be obtained from the **DOpus.vars**, **Lister.vars**, **Tab.vars**, **Command.vars** or **Script.vars** properties.
- **[Vector](/Manual/reference/scripting_reference/scripting_objects/vector.md)**: This object is similar to an array - it can store an unlimited number of elements of any type. Several properties and methods in the Opus scripting interface use Vectors, and you can use them interchangeably with arrays in most cases. The Vector is provided because some scripting languages only offer incomplete or incompatible arrays - using Vectors means the object can be used consistently across any ActiveX scripting language. A **Vector** is created by the **DOpusFactory.Vector** method.
- **[Version](/Manual/reference/scripting_reference/scripting_objects/version.md)**: This object represents information about the current Opus version. It is obtained from the **DOpus.Version** property.
- **[VideoMeta](/Manual/reference/scripting_reference/scripting_objects/videometa.md)**: This object provides metadata properties relating to movie files. It is obtained from the **Metadata** object.
- **[Viewer](/Manual/reference/scripting_reference/scripting_objects/viewer.md)**: The **Viewer** object represents a standalone [image viewer](/Manual/additional_functionality/viewing_images/README.md).
- **[Viewers](/Manual/reference/scripting_reference/scripting_objects/viewers.md)**: The **Viewers** object is a collection of all currently open standalone [image viewers](/Manual/additional_functionality/viewing_images/README.md). It can be obtained via the **[DOpus](/Manual/reference/scripting_reference/scripting_objects/dopus.md).viewers** property
- **[Wild](/Manual/reference/scripting_reference/scripting_objects/wild.md)**: This object allows a script to access the in-built pattern matching functions in Opus. It is obtained from the **FSUtil.NewWild** method.
- **[WinVer](/Manual/reference/scripting_reference/scripting_objects/winver.md)**: This object represents information about the current Windows version. It is obtained from the **Version.winver** property.