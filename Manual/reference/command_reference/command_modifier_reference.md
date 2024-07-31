# Command modifier reference

The following is a list of the various [command modifiers](/Manual/customize/creating_your_own_buttons/command_modifiers.md) supported in toolbar buttons and hotkeys.

<table>
<thead><tr><th>
Modifier</th><th>
Description
</th></tr></thead><tbody><tr><td>
@admin</td><td>

The function requires administrator permissions. This modifier will result in a UAC prompt appearing (unless the Lister is already in [administrator mode](/Manual/file_operations/uac_and_administrator_mode.md)), and any external programs run by this function will be elevated.

If used by itself, this modifier affects the entire function. It can also be used to elevate a specific command rather than the entire button.

|                            |                                                                    |
|----------------------------|--------------------------------------------------------------------|
| **@admin**                 | *elevate the entire function*                                      |
| **@admin:notepad.exe {f}** | *only elevates Notepad*                                            |
| **@admin:no**              | *disable UAC prompts for any subsequent commands in this function* |
| **@admin:yes**             | *re-enable UAC prompts for any subsequent commands*                |
</td></tr><tr><td>
@async</td><td>

The command following this modifier will be run asynchronously - Opus will not wait for it to exit before running the next command in the function (or before running this command again for the next selected file).

The default behaviour is for a function that consists of a single command to run that command asynchronously for each selected file; a function that consists of multiple commands will run each command synchronously. The default behaviour can be changed with the **function_default_async** option on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences, or it can be overridden on a per-command basis with this modifier.

|                            |                               |
|----------------------------|-------------------------------|
| **@async:notepad.exe {f}** | *runs Notepad asynchronously* |
</td></tr><tr><td>
@codepage</td><td>

Changes the code page of an [MS-DOS batch command](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.md). If not specified the default code page is 1252 ([Windows-1252](http://en.wikipedia.org/wiki/Windows-1252)).

|                    |                                    |
|--------------------|------------------------------------|
| **@codepage:1258** | *sets the code page to Vietnamese* |
</td></tr><tr><td>
@confirm</td><td>

Displays a confirmation dialog. If the user clicks the cancel button, the function is aborted at this point.

The template for this modifier is: **@confirm:***\<message\>***\|***\<positive text\>***\|***\<negative text\>*

*\<message\>* is the text shown in the dialog, *\<positive text\>* is the text shown on the "OK" button, and *\<negative text\>* is the text shown on the "Cancel" button. These three strings are all optional - if not provided, default strings will be used. If you provide *\<positive text\>* but not *\<negative text\>* then the dialog will have an "OK" button but no "Cancel" button at all.

You can include line-breaks in the message text using the special code **\n** (and if you need to include a literal **\n** sequence in the text you must escape the **\\** character, as in **\\n**).

|                                          |                                                          |
|------------------------------------------|----------------------------------------------------------|
| **@confirm:Really copy files?**          | *uses default text for the OK and Cancel buttons*        |
| **@confirm:Really proceed?\|Oui!\|Non!** | *specifies custom text for the two buttons*              |
| **@confirm:All finished\|Acknowledged**  | *custom text for the OK button; no Cancel button at all* |
</td></tr><tr><td>
@ctx</td><td>

Allows you to define a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md) using the [evaluator](/Manual/evaluator/README.md). As a simple example,

    @ctx:=return "Go DRIVEBUTTONS";

This uses the evaluator to return a simple string; functionally this is no different to simply putting the **Go DRIVEBUTTONS** command on a toolbar button.

As a more complex example, the default *Favorites Bar* toolbar uses **@ctx** to build the displayed favorites list, by using the Evaluator to build a command line using the current localised name of the favorites bar branch:

    @ctx:=return "Favorites SHOWICONS USEQUALKEYS BRANCH=""" + LanguageStr("FavoritesBar") + """;

This uses the evaluator **LanguageStr()** function to retrieve the translated name of a known string, and constructs a command line using the **Favorites** command to display that branch of the favorites tree.
</td></tr><tr><td>
@dirsonly</td><td>

The function will operate only on selected folders, ignoring any files.

|               |                               |
|---------------|-------------------------------|
| **@dirsonly** | *operate only on directories* |
</td></tr><tr><td>
@disableif</td><td>

The button will be disabled if a command clause test is false. This is similar to the conditional testing offered by the **@if** modifier described below.

|                                 |                                                                   |
|---------------------------------|-------------------------------------------------------------------|
| **@disableif:Set DUAL=toggle**  | button will be disabled if the Lister is in dual-display mode     |
| **@disableif:!Set DUAL=toggle** | button will be disabled if the Lister is NOT in dual-display mode |
</td></tr><tr><td>

@disableifpath  
@disableifpathr</td><td>

The button will be disabled if the current source path matches the specified pattern. You can provide either an absolute path to test against, or a wildcard pattern (use **@disableifpath** for [standard wildcards](../wildcard_reference/pattern_matching_syntax.md), and **@disableifpathr** for [regular expressions](../wildcard_reference/regular_expression_syntax.md)). You can also use the keyword **shell** to test for a hosted shell namespace extension (virtual folder).

|                                 |                                                                     |
|---------------------------------|---------------------------------------------------------------------|
| **@disableifpathr:^C:\\**       | *disable command if source path is on the C: drive*                 |
| **@disableifpath:!\*\Work\\**\* | *disable unless source path is underneath a folder called **Work*** |

Paths may use aliases, environment variables, {apppath} codes, and so on, only when using wildcards (not regular expressions):

|                                           |                                                                   |
|-------------------------------------------|-------------------------------------------------------------------|
| **@disableifpath:!/desktop**              | *disable unless in the Desktop folder*                            |
| **@disableifpath:!%SystemRoot%\System32** | *disable unless in **C:\Windows\System32** (on a typical system)* |
| **@disableifpath:{apppath\|dopus.exe}**   | *disable if in the folder where Opus is installed*                |
| **@disableifpath:shell**                  | *disable if in a hosted virtual folder*                           |
</td></tr><tr><td>
@disablenosel</td><td>

The command will be disabled when no files or folders are selected, or optionally when no files of a certain type are selected. This is done automatically for certain standard commands and the modifier lets you make your own commands behave in a similar way. This is similar to **@hidenosel**.

|                         |                                               |
|-------------------------|-----------------------------------------------|
| **@disablenosel**       | *disable button when nothing is selected*     |
| **@disablenosel:files** | *disable button when no files are selected*   |
| **@disablenosel:dirs**  | *disable button when no folders are selected* |

For lister toolbars, you can use the **minfiles**, **maxfiles** and **numfiles** keywords to specify a minimum, maximum, or exact number of files which must be selected for the button to be enabled. Similarly, **mindirs**, **maxdirs** and **numdirs** can limit the number of selected folders.

|                                       |                                                        |
|---------------------------------------|--------------------------------------------------------|
| **@disablenosel:numfiles=2**          | *disable button unless exactly 2 files are selected*   |
| **@disablenosel:maxfiles=5**          | *disable button unless 5 files or fewer are selected*  |
| **@disablenosel:mindirs=3,maxdirs=5** | *disable button unless 3, 4 or 5 folders are selected* |

Using the **type** keyword you can configure a button to be disabled unless at least one file is selected whose name matches the supplied wildcard pattern. (It is not required that all selected files match the pattern; only one.) You can also combine this with **dirs** for a button that works if a folder is selected or if a file of a certain type is selected. If you use **type**, it must be the last thing on the line, since everything after the **=** will be considered part of the pattern (allowing the pattern to include things which would otherwise be confused with other keywords and parameters).

|                                    |                                                                             |
|------------------------------------|-----------------------------------------------------------------------------|
| **@disablenosel:type=\*.jpg**      | *disable button when no files ending with ".jpg" are selected*              |
| **@disablenosel:type=old**         | *disable button when no files beginning with "old" are selected*            |
| **@disablenosel:dirs,type=\*.png** | *disable unless any folders, or any files ending with ".png", are selected* |

You can also use a **!** character to negate the test. It must be the first thing after the **:**. For example,

|                                |                                                           |
|--------------------------------|-----------------------------------------------------------|
| **@disablenosel:!type=\*.jpg** | *disable button if files ending with ".jpg" are selected* |
</td></tr><tr><td>
@enableif</td><td>

The button will be enabled if a command clause test is true. This is similar to the conditional testing offered by the **@if** modifier described below.

|                                |                                                                  |
|--------------------------------|------------------------------------------------------------------|
| **@enableif:Set DUAL=toggle**  | button will be enabled if the Lister is in dual-display mode     |
| **@enableif:!Set DUAL=toggle** | button will be enabled if the Lister is NOT in dual-display mode |
</td></tr><tr><td>

@enableifpath  
@enableifpathr</td><td>

The button will be enabled if the current source path matches the specified pattern. You can provide either an absolute path to test against, or a wildcard pattern (use **@enableifpath** for [standard wildcards](../wildcard_reference/pattern_matching_syntax.md), and **@enableifpathr** for [regular expressions](../wildcard_reference/regular_expression_syntax.md)). You can also use the keyword **shell** to test for a hosted shell namespace extension (virtual folder).

|                                |                                                                    |
|--------------------------------|--------------------------------------------------------------------|
| **@enableifpathr:^C:\\**       | *enable command if source path is on the C: drive*                 |
| **@enableifpath:!\*\Work\\**\* | *enable unless source path is underneath a folder called **Work*** |

Paths may use aliases, environment variables, {apppath} codes, and so on, only when using wildcards (not regular expressions):

|                                          |                                                                  |
|------------------------------------------|------------------------------------------------------------------|
| **@enableifpath:!/desktop**              | *enable unless in the Desktop folder*                            |
| **@enableifpath:!%SystemRoot%\System32** | *enable unless in **C:\Windows\System32** (on a typical system)* |
| **@enableifpath:{apppath\|dopus.exe}**   | *enable if in the folder where Opus is installed*                |
| **@enableifpath:shell**                  | *enable if in a hosted virtual folder*                           |
</td></tr><tr><td>

@eval  
@evalalways</td><td>

Runs [Evaluator](/Manual/evaluator/README.md) code as part of a dynamic test, and optionally as part of the command itself. Typically you would use this to set Evaluator variables which can be used on later lines in the command.

- Code after `@eval:` is only run when dynamically updating the button's label, visibility and enabled/disabled state. It's not run when the button is clicked.
- Code after `@evalalways:` also runs when the button is clicked. This lets you set up variables which are used both when executing commands and, e.g. also when updating their labels.

In this example, the `type` value is initialised once in the top line, and then referred to multiple times in the subsequent lines.

    @eval:type = PathType(source);
    fIsFileSystem = (type == "shell" || type == "filesys")
    @showif:=fIsFileSystem
    @label:fIsFileSystem ? ("Open " + FilePart(DisplayName(source)) + " in Explorer") : ("Disabled (" + type + ")")
</td></tr><tr><td>
@externalonly</td><td>

Ignores any Opus [internal commands](internal_commands/README.md) specified in the function, and treats all commands as external. This lets you configure an MS-DOS batch function using commands like **copy** which would normally be overridden by the internal command set.

|                   |                          |
|-------------------|--------------------------|
| **@externalonly** | *external commands only* |
</td></tr><tr><td>
@filesfromdroponly</td><td>

Accepts files and folders only via drag-and-drop. A button with this modifier will ignore any selected files or folders in the Lister - only files dropped onto the button will be used by a command within it.

|                        |                                       |
|------------------------|---------------------------------------|
| **@filesfromdroponly** | *accept files only via drag-and-drop* |
</td></tr><tr><td>
@filesonly</td><td>

The function will operate only on selected files, ignoring any folders.

|                |                         |
|----------------|-------------------------|
| **@filesonly** | *operate only on files* |
</td></tr><tr><td>
@firstfileonly</td><td>

The function will operate on only the first selected file, irrespective of how many items are selected or dropped onto the button.

|                    |                                           |
|--------------------|-------------------------------------------|
| **@firstfileonly** | *operate on only the first selected file* |
</td></tr><tr><td>
@functype</td><td>

This directive is only used within an [embedded function](/Manual/customize/creating_your_own_buttons/embedded_functions.md). It lets you specify the type of the embedded function (if not specified, the embedded function is assumed to be a standard function - Opus or external command). For example, the following command would open a new Lister with an embedded script function that runs in the context of the new Lister:

    Go NEW
    [
    @functype:script
    @script:vbscript
    ' script function here
    ]

|                      |                                                     |
|----------------------|-----------------------------------------------------|
| **@functype:script** | *the embedded function is a script*                 |
| **@functype:msdos**  | *the embedded function is an MS-DOS batch function* |
</td></tr><tr><td>
@hideblock</td><td>

The **@hideblock** modifier lets you use the various other modifiers to hide or show multiple buttons at once, without having to repeat the tests in each button.

Use **@hideblock:begin** on a button to begin the block, along with whichever other modifiers are appropriate. The buttons within the block will be hidden or shown depending on the state of the first button. For example,

    @hideif:!Set VIEW=Thumbnails
    @hideblock:begin

This button begins a hide/show block based on the current view mode. If the current view is in thumbnails mode, the buttons will be visible - otherwise they'll be hidden.

Use **@hideblock:end** on another button to end the block. All buttons between the beginning and end will be hidden or shown as one. Note that the beginning and ending buttons are never shown outside of Customize mode.

|                      |                      |
|----------------------|----------------------|
| **@hideblock:begin** | *begin a hide block* |
| **@hideblock:end**   | *end a hide block*   |
</td></tr><tr><td>
@hideif</td><td>

The button will be hidden if a command clause test is false. This is similar to the conditional testing offered by the **@if** modifier described below.

|                              |                                                                   |
|------------------------------|-------------------------------------------------------------------|
| **@hideif:Set DUAL=toggle**  | *button will be hidden if the Lister is in dual-display mode*     |
| **@hideif:!Set DUAL=toggle** | *button will be hidden if the Lister is NOT in dual-display mode* |
</td></tr><tr><td>

@hideifpath  
@hideifpathr</td><td>

The button will be hidden if the current source path doesn't match the specified pattern. You can provide either an absolute path to test against, or a wildcard pattern (use **@hideifpath** for [standard wildcards](../wildcard_reference/pattern_matching_syntax.md), and **@hideifpathr** for [regular expressions](../wildcard_reference/regular_expression_syntax.md)).

|                              |                                                                  |
|------------------------------|------------------------------------------------------------------|
| **@hideifpathr:^C:\\**       | *hide command if source path is on the C: drive*                 |
| **@hideifpath:!\*\Work\\**\* | *hide unless source path is underneath a folder called **Work*** |

Paths may use aliases, environment variables, {apppath} codes, and so on, only when using wildcards (not regular expressions):

|                                        |                                                                |
|----------------------------------------|----------------------------------------------------------------|
| **@hideifpath:!/desktop**              | *hide unless in the Desktop folder*                            |
| **@hideifpath:!%SystemRoot%\System32** | *hide unless in **C:\Windows\System32** (on a typical system)* |
| **@hideifpath:{apppath\|dopus.exe}**   | *hide if in the folder where Opus is installed*                |
</td></tr><tr><td>
@hidenosel</td><td>

The button will be hidden when no files or folders are selected, or optionally when no files of a certain type are selected. This is similar to **@disablenosel**.

|                      |                                            |
|----------------------|--------------------------------------------|
| **@hidenosel**       | *hide button when nothing is selected*     |
| **@hidenosel:files** | *hide button when no files are selected*   |
| **@hidenosel:dirs**  | *hide button when no folders are selected* |

For lister toolbars, you can use the **minfiles**, **maxfiles** and **numfiles** keywords to specify a minimum, maximum, or exact number of files which must be selected for the button to be visible. Similarly, **mindirs**, **maxdirs** and **numdirs** can limit the number of selected folders.

|                                    |                                                     |
|------------------------------------|-----------------------------------------------------|
| **@hidenosel:numfiles=2**          | *hide button unless exactly 2 files are selected*   |
| **@hidenosel:maxfiles=5**          | *hide button unless 5 files or fewer are selected*  |
| **@hidenosel:mindirs=3,maxdirs=5** | *hide button unless 3, 4 or 5 folders are selected* |

Using the **type** keyword you can configure a button to be hidden unless at least one file is selected whose name matches the supplied wildcard pattern. (It is not required that all selected files to match the pattern; only one.) You can also combine this with **dirs** for a button that is visible if a folder is selected or if a file of a certain type is selected. If you use **type**, it must be the last thing on the line, since everything after the **=** will be considered part of the pattern (allowing the pattern to include things which would otherwise be confused with other keywords and parameters).

|                                 |                                                                          |
|---------------------------------|--------------------------------------------------------------------------|
| **@hidenosel:type=\*.jpg**      | *hide button when no files ending with ".jpg" are selected*              |
| **@hidenosel:type=old**         | *hide button when no files beginning with "old" are selected*            |
| **@hidenosel:dirs,type=\*.png** | *hide unless any folders, or any files ending with ".png", are selected* |

You can also use a **!** character to negate the test. It must be the first thing after the **:**. For example,

|                             |                                                        |
|-----------------------------|--------------------------------------------------------|
| **@hidenosel:!type=\*.jpg** | *hide button if files ending with ".jpg" are selected* |
</td></tr><tr><td>

@icon  
@icon!  
@iconp</td><td>

The **@icon** directive lets you create buttons that dynamically change their icon based on the test of a command clause, typically via the **Set** command (similar to **@if** and **@ifset**). The default *View Mode Cycle* button uses this to change its icon to reflect the current view mode.

    Set VIEW=Cycle
    @icon:largeicons,Set VIEW=LargeIcons
    @icon:smallicons,Set VIEW=SmallIcons
    @icon:listmode,Set VIEW=List
    @icon:powermode,Set VIEW=Power
    @icon:thumbnails,Set VIEW=Thumbnails
    @icon:tile,Set VIEW=Tiles
    @icon:detailsmode,Set VIEW=Details

Each **@icon** directive in the button specifies the icon to use, and the command directive to test for. For example, if **Set VIEW=LargeIcons** tests as true, the icon called **largeicons** will be displayed on the button. If none of the **@icon** tests match then the icon set in the button itself will be used as the default image.

In the special case of a three-button button, **@iconp:** and **@icon!:** directives can also be used in any of the child buttons to change the icon of the parent. **@iconp:** used in one of the child buttons will set the icon of the parent (but do nothing to the child button). **icon!:** used in one of the child buttons will set the icon of the parent as well as of that child button.

If you are testing based on the **Set** command, the command name is technically optional and can be ommitted. For example, **VIEW=LargeIcons** on its own is the same as **Set VIEW=LargeIcons**. This ability is there to avoid breaking old buttons and, with new buttons, we recommend you include the command name in all cases to avoid problems in the future.

In the command editor, you can **Ctrl**+click the **@icon:** string to select the icon directly.

**@icon** can use the **RECYCLEBINEMPTY** argument to test if the recycle bin is empty or not. For example,

    @icon:c:\icons\empty.png,RECYCLEBINEMPTY

Toolbar buttons that use **@icon** with **RECYCLEBINEMPTY** will refresh themselves automatically when the recycle bin state changes (this lets you have a button whose icon reflects the state of the recycle bin).
</td></tr><tr><td>

@if  
@ifset</td><td>

Allows simple conditional behaviour based on tests for various commands.

**@if** is a general test which works with any command, and **@ifset** is a specific test which only works with the **[Set](internal_commands/set.md)** command conditions. For example, **@ifset:DUAL=on** is equivalent to **@if:Set DUAL=on**.  
The test **@if** actually performs is to evaluate whether a toolbar button with the specified command would appear highlighted or not. For example, if the Lister is in dual-display mode, a button with **Set DUAL=toggle** as the command would appear highlighted. Therefore, the **@if:Set DUAL=toggle** modifier would evaluate to true.

You can also evaluate whether a toolbar button would be enabled or not, using **@if:enabled**. For example, [Navigation Lock](/Manual/basic_concepts/the_lister/dual_display/navigation_lock.md) is only enabled when a Lister is in dual-display mode. Therefore, the modifier **@if:enabled Set NAVLOCK=Toggle** would evaluate to true when the Lister was in dual-display mode.

You can also test if a variable has been set by the **@set** directive. Additionally, a button on the [File Display toolbar](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/file_display_toolbar.md) can test if it's tied to the left or right file display.

For example, you could configure a button to read a folder into the right file display in a dual-display Lister, or into the current file display otherwise.

    @if:Set DUAL=on             // if DUAL mode is on
    Set FOCUS=right             // give focus to the right file display
    Go /mypictures OPENINRIGHT  // read directory into that file display
    @if:else                    // otherwise
    Go /mypictures              // read directory into current file display
    @if:common                  // common commands (always executed)
    Set VIEW=thumbnails         // set view to thumbnails mode

As another example, **@ifset** can use the **RECYCLEBINEMPTY** argument to test if the recycle bin is empty or not:

    @ifset:RECYCLEBINEMPTY
    @confirm The recycle bin is empty!
    @ifset:else
    Delete EMPTYRECYCLE

Conditional testing can also be used on buttons in the [standalone viewer](/Manual/additional_functionality/viewing_images/README.md). The following function will toggle the display between 100% zoom and *Grow To Page* modes, by using **@if** to test the current zoom mode:

    @if:Show VIEWERCMD=zoom,reset
    Show VIEWERCMD=zoom,grow
    @if:else
    Show VIEWERCMD=zoom,reset

The possible forms of this modifier are:

|                                       |                                                                                                                                    |
|---------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| **@if:\<command line\>**              | *test if a specific command condition is true*                                                                                     |
| **@ifset:***\<Set command argument\>* | *test for a specific Set command condition*                                                                                        |
| **@if:enabled** *\<command\>*         | *test if a command button would be enabled (rather than highlighted)*                                                              |
| **@if:\$foo**                         | *test if a variable called "foo" has been set*                                                                                     |
| **@if:\$glob:bar**                    | *test if a global variable called "bar" has been set*                                                                              |
| **@if:SIDE=left**                     | *test if the toolbar is tied to the left file display*                                                                             |
| **@if:SIDE=right**                    | *test if the toolbar is tied to the right file display*                                                                            |
| **@if:&&ARG&&=value**                 | *test if a [User-defined command](/Manual/customize/creating_your_own_buttons/user-defined_commands.md) argument matches a given value*      |
| **@if:&&ARG&&!=value**                | *test if a [User-defined command](/Manual/customize/creating_your_own_buttons/user-defined_commands.md)argument doesn't match a given value* |
| **@if:else**                          | *an "else" clause that is executed if nothing else matches*                                                                        |
| **@if:common**                        | *common instructions that are always executed*                                                                                     |

You can negate the condition by prefixing it with a **!** character. For example, all four of these are equivalent:

    @if:!Set DUAL=on
    @if:Set DUAL=off
    @ifset:!DUAL=on
    @ifset:DUAL=off
</td></tr><tr><td>
@ifexists</td><td>

Allows simple conditional behaviour based on whether the specified drive or path exists. The final component of a path can contain [standard wildcards](../wildcard_reference/pattern_matching_syntax.md) if the **wild:** prefix is used.

|                      |                                                                                                  |
|----------------------|--------------------------------------------------------------------------------------------------|
| **@ifexists:**       | *\<drive or path\> - test if drive or path exists*                                               |
| **@ifexists:wild:**  | *\<drive or path\> - test if drive or path exists. Allows wildcards in the final path component* |
| **@ifexists:!**      | *\<drive or path\> - test if drive or path does not exist*                                       |
| **@ifexists:else**   | *an "else" clause that is executed if the path doesn't exist*                                    |
| **@ifexists:common** | *common instructions that are always executed*                                                   |
</td></tr><tr><td>
@ifsel</td><td>

Lets a function do different things depending on file or folder selection. The available tests are the same as for the **@disablenosel** modifier (documented above).

For example,

    @ifsel:numfiles=2
    <run program that accepts exactly two files>
    @ifsel:else
    <show an error message>
</td></tr><tr><td>

@ifpath  
@ifpathr</td><td>

Allows simple conditional behaviour based on the current source path. You can provide either an absolute path to test against, or a wildcard pattern (use **@ifpath** for [standard wildcards](../wildcard_reference/pattern_matching_syntax.md), and **@ifpathr** for [regular expressions](../wildcard_reference/regular_expression_syntax.md)).

For example, you could use this to open different programs when double-clicking on an image file, depending on where the file is stored. If the following command was added to the *Left double-click* [event](/Manual/file_types/filetype_editor/events.md) for the **Images** [file type group](/Manual/file_types/file_type_groups.md), pictures located on the network will be opened in the Opus viewer when they are double-clicked, whereas files located on a local drive would open in Photoshop.

    @ifpath:\\*                      // if path begins with \\
    Show                             // invoke the Opus viewer
    @ifpath:else                     // otherwise...
    Photoshop.exe {f}                // open in Photoshop (the full path would generally need
                                     // to be specified - this is just an example)

The possible forms of this modifier are:

|                                       |                                                             |
|---------------------------------------|-------------------------------------------------------------|
| **@ifpath:***\<path or wildcard\>*    | *test for a path (using standard pattern matching)*         |
| **@ifpathr:***\<regular expression\>* | *test for a path (using regular expressions)*               |
| **@ifpath:else**                      | *an "else" clause that is executed if nothing else matches* |
| **@ifpath:common**                    | *common instructions that are always executed*              |

You can negate the condition by prefixing it with a **!** character.

Examples:

|                                   |                                                                                           |
|-----------------------------------|-------------------------------------------------------------------------------------------|
| **@ifpath:C:\Program Files**      | *Tests you are in C:\Program Files*                                                       |
| **@ifpath:!C:\Program Files**     | *Tests you are anywhere but C:\Program Files*                                             |
| **@ifpath:C:\Program Files\\**\*  | *Tests you're in a folder below C:\Program Files (does not include Program Files itself)* |
| **@ifpath:!C:\Program Files\\**\* | *Tests you are not in a folder below C:\Program Files*                                    |
</td></tr><tr><td>
@ifrunning</td><td>

Allows simple conditional behaviour based on whether a specified process is currently running. You can use wildcards or (by prefixing the pattern with **regex:**) regular expressions.

|                            |                                                                  |
|----------------------------|------------------------------------------------------------------|
| **@ifrunning:notepad.exe** | *test if Notepad is running*                                     |
| **@ifrunning:!note**\*     | *test if a process starting with "note" is not running*          |
| **@ifrunning:else**        | *an "else" clause that is executed if the process doesn't exist* |
| **@ifrunning:common**      | *common instructions that are always executed*                   |
</td></tr><tr><td>
@keydown</td><td>

Allows simple conditional behaviour based on whether various qualifier keys are held down when the function is run.

The qualifiers to test for are specified using one or more keywords (**shift**, **ctrl** and **alt**) which represent the <kbd>Shift</kbd>, <kbd>Ctrl</kbd> and <kbd>Alt</kbd> keys. For example, you could configure a button to select all files, then copy, move or create shortcuts to them, depending on which keys were held down.

    Select ALL              // select all items (always executed)
    @keydown:none           // if no qualifiers are down
    Copy                    // copy files to destination
    @keydown:shift          // else if shift key is down
    Copy MOVE               // move files to destination
    @keydown:ctrlshift      // else if both control and shift keys are down
    Copy MAKELINK           // make shortcuts in destination

The possible forms of this modifier are:

|                                |                                                                                                                                                                                                                   |
|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **@keydown:***\<qualifiers\>*  | *test for a qualifier key or combination of keys*                                                                                                                                                                 |
| **@keydown:!***\<qualifiers\>* | *test for a qualifier key or combination of keys NOT being down*                                                                                                                                                  |
| **@keydown:any**               | // tests if **any** qualifier keys are held down*\| \|**@keydown:none**\|*instructions that are executed if no qualifiers are held down*\| \|**@keydown:common**\|*common instructions that are always executed// |
</td></tr><tr><td>
@label</td><td>

TOBEDONE

If something modifies variables, or other factors that affect dynamic labels, it should notify Opus so labels and toolbar layouts can be updated. Commands should use **@toggle:update** (see below) and scripts can use [Command.UpdateToggle](/Manual/reference/scripting_reference/scripting_objects/command.md) to do this.
</td></tr><tr><td>
@leavedoswindowopen</td><td>

The console window opened for an [MS-DOS batch function](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.md) will remain open when the function has completed. Without this modifier the window will close when the function finishes, which may make it hard to read the output of any command-line programs.  
Leaving the DOS window opens relies on passing a particular argument (**/K**) to the system command interpreter, **cmd.exe**. If you have modified the default command processor on your system by setting the **%ComSpec%** environment variable, Opus will not pass **/K** as there is no way for it to know if this argument would be understood by the new command processor. Instead, you can set the **%ComSpecLeaveOpenArg%** environment variable, and this will be used instead of **%ComSpec%** whenever **@leavedoswindowopen** is used.

|                         |                                                |
|-------------------------|------------------------------------------------|
| **@leavedoswindowopen** | *leave DOS prompt open when function finishes* |
</td></tr><tr><td>
@logusage</td><td>

Instructs Windows to log usage of programs or documents opened by this function. Typically this means any files used will be added to the recent documents list, and any programs that are launched are added to the recent applications list.

|               |                                       |
|---------------|---------------------------------------|
| **@logusage** | *log usage of files and applications* |
</td></tr><tr><td>
@nocall</td><td>

An [MS-DOS batch function](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.md) function that invokes an external **.bat** file will run it directly, rather than using ***call*** semantics. This means that control will not return to the parent function once the external **.bat** file has finished. The default behaviour is to use the DOS **call** instruction which returns control to the parent function at the end.

|                              |                                                                      |
|------------------------------|----------------------------------------------------------------------|
| **@nocall:***\<batch file\>* | *invoke external batch file, do not return control to this function* |
</td></tr><tr><td>
@nodeselect</td><td>

Files and folders will remain selected at the end of the function. This lets you override the **Deselect files used in functions** option on the **[File Operations / Options](/Manual/preferences/preferences_categories/file_operations/options.md)** page in Preferences, on a per-function basis.

|                 |                                               |
|-----------------|-----------------------------------------------|
| **@nodeselect** | *do not deselect items used by this function* |
</td></tr><tr><td>
@noexpandenv</td><td>

Prevent the expansion of any environment variables in the function. Normally environment variables like **%USERPROFILE%** are expanded during the function parsing phase - this modifier causes variable names to be left intact.

|                  |                                       |
|------------------|---------------------------------------|
| **@noexpandenv** | *do not expand environment variables* |
</td></tr><tr><td>
@nofilenamequoting</td><td>

Disables the automatic quoting that Opus performs when [external codes](external_control_codes/README.md) like **{filepath}** are used to pass the name of a file that contains spaces. By default Opus will wrap names with embedded spaces in quotes, but occasionally you may want to disable this - some external programs may not need or understand quotes on their command line, and you may also want to provide explicit quotes in a function in case the automatic quoting gets confused by complicated command structures.

|                        |                                                   |
|------------------------|---------------------------------------------------|
| **@nofilenamequoting** | *do not automatically quote file names and paths* |
</td></tr><tr><td>
@nolocalizefiles</td><td>

Prevents Opus from automatically downloading or extracting non-filesystem files when passing their paths to external programs. For example, you may want to use **{filepath}** to pass the **ftp://** path of a file on a remote FTP server to an external program. By default Opus will download the file to a temporary file, and pass the name of the temporary file to the program - with this modifier, Opus will instead pass the original file path.

|                      |                                                         |
|----------------------|---------------------------------------------------------|
| **@nolocalizefiles** | *do not automatically localize (download) remote files* |
</td></tr><tr><td>
@noprogress</td><td>

Disables the automatic display of a progress indicator for this function. You should use this with care as without a progress indicator there is no way to abort the command or monitor its progress. Normally only script functions should use this when they want to provide and control their own progress indicator.

|                 |                                                                 |
|-----------------|-----------------------------------------------------------------|
| **@noprogress** | *do not display an automatic progress dialog for this function* |
</td></tr><tr><td>
@norunbatch</td><td>

When an [MS-DOS batch function](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.md) combines internal and external commands, the default behaviour is for Opus to split the function at every internal command, and execute all the external commands that came before it. For example, imagine the following (rather pointless) function:

    echo one
    Help ABOUT
    echo two
    @leavedoswindowopen

The default behaviour of this function would be to open a DOS window and print the string "one", then display the Opus **About** dialog, and then open another DOS window and print the string "two". If, however, the function were changed as follows:

    @norunbatch
    echo one
    Help ABOUT
    echo two
    @leavedoswindowopen

The new behaviour would be to first display the **About** dialog, and then open a single DOS window and print both the strings "one" and "two". The **@norunbatch** modifier causes all Opus internal commands to be executed first, followed by all external commands.

|                 |                                                             |
|-----------------|-------------------------------------------------------------|
| **@norunbatch** | *do not split batch functions because of internal commands* |
</td></tr><tr><td>
@output</td><td>

Outputs all text on the rest of the line to the Script Log. Useful for debugging. The output can also be viewed in the Command Editor when its \*Run With Logging\* mode is on.

|                           |                                       |     |
|---------------------------|---------------------------------------|-----|
| **@output** *\<message\>* | *sends \<message\> to the Script Log* |     |
</td></tr><tr><td>
@perfile</td><td>

Allows a block of commands to be run once per file. Normally, functions containing multiple command lines run each command separately for all selected files.

For example,

    echo 1 {file}
    echo 2 {file}

With two files, "Apple.txt" and "Banana.txt" selected, this would output:

    1 Apple.txt
    1 Banana.txt
    2 Apple.txt
    2 Banana.txt

Using **@perfile** around these commands like so:

    @perfile:begin
    echo 1 {file}
    echo 2 {file}
    @perfile:end

This would output:

    1 Apple.txt
    2 Apple.txt
    1 Banana.txt
    2 Banana.txt

Use **@perfile:begin** to mark the beginning of the per-file block and **@perfile:end** to mark the end.
</td></tr><tr><td>
@resolvelinks</td><td>

Shortcuts or links passed to commands in this function will be resolved to their targets. Without this modifier, a selected **.lnk** file would be passed as-is.

|                   |                                                               |
|-------------------|---------------------------------------------------------------|
| **@resolvelinks** | *resolve shortcut targets when passing filenames to commands* |
</td></tr><tr><td>
@runbatch</td><td>

Force the execution of an MS-DOS batch function at a certain point. The default behaviour is for such functions to be executed at the very end of the function - using this modifier you can force a break in the function at any line. For example:

    echo one
    @runbatch
    echo two
    @leavedoswindowopen

This will cause two separate DOS windows to open, one displaying the text "one" and the other displaying "two". Without the **@runbatch** directive, the two commands would have been executed in the one window.

|               |                                                            |
|---------------|------------------------------------------------------------|
| **@runbatch** | *force a DOS batch function to execute at a certain point* |
</td></tr><tr><td>
@runmode</td><td>

Modifies the "run" state of external programs launched by the function - that is, how its main window should appear. This is equivalent to the **Run** drop-down on the [simple command editor](/Manual/customize/creating_your_own_buttons/command_editor/simple_command_editor.md). Not all programs will support this setting, so you will need to use trial and error to some extent. You should only set the mode to **hide** if you are sure of what you are doing - it is most useful for hiding the otherwise brief flash of a DOS window when running a DOS program.

|                   |                                      |
|-------------------|--------------------------------------|
| **@runmode:min**  | *minimize the program's main window* |
| **@runmode:max**  | *maximize the program's main window* |
| **@runmode:hide** | *hide the program's main window*     |
</td></tr><tr><td>
@runonce</td><td>

Forces the command following the modifier to only be run once per function, instead of once per file.

|                            |                                               |
|----------------------------|-----------------------------------------------|
| **@runonce:***\<command\>* | *the specified command will only be run once* |
</td></tr><tr><td>
@script</td><td>

Specifies the scripting language used for a script. This is mainly used for [embedded rename scripts](/Manual/customize/creating_your_own_buttons/embedding_rename_scripts.md), because otherwise the script language is selected via a drop-down at the top of the script editor. The **@script** modifier must be followed by a keyword that specifies the scripting language (or in the case of [script add-ins](/Manual/scripting/script_add-ins/README.md), the file extension of the add-in itself specifies the language).

For example,

    Rename PATTERN * TO *
    @script:vbscript
    Function ....

|                            |                                                   |
|----------------------------|---------------------------------------------------|
| **@script:***\<language\>* | *specifies scripting language for Rename command* |
</td></tr><tr><td>
@set</td><td>

Sets the value of a named variable that can be used by the remainder of the commands in the function. You can pass the value of a variable to internal and external commands using the **{\$}** [control code](external_control_codes/codes_for_clipboard_and_variables.md). Variables are most useful in the situation where the value is defined by a **{dlgstring}** code. For example,

    @set dir={dlgstring|Enter new folder name to copy files to}
    CreateFolder ".\{$dir}"
    Copy TO ".\{$dir}"

Normally, variables do not persist from one invocation of the function to another, and you can not refer to variables set in one function from another. However this can be accomplished by prefixing the variable name with a special scope marker that determines which scope the variable will live in.

|                      |                                                                |
|----------------------|----------------------------------------------------------------|
| **src:***\<name\>*   | *variable will be scoped to the source folder tab*             |
| **dst:***\<name\>*   | *variable will be scoped to the destination folder tab*        |
| **left:***\<name\>*  | *variable will be scoped to the left folder tab*               |
| **right:***\<name\>* | *variable will be scoped to the right folder tab*              |
| **tab:***\<name\>*   | *variable will be scoped to the active folder tab (see below)* |
| **lst:***\<name\>*   | *variable will be scoped to the Lister (the whole window)*     |
| **glob:***\<name\>*  | *variable will be scoped globally*                             |

The **src:** and **tab:** scopes usually point to the same folder tab within commands. (The **tab:** scope was introduced so that [status bar codes which use variables](../status_bar_codes/other_codes.md) can refer to the side that the status bar is on, without worrying if it is the source, destination, left or right. It is supported in commands for consistency.)

You can also mark variables to be saved on disk - their values will be remembered from one Opus session to the next. To accomplish this, simply add an exclamation mark (!) to the scope marker. For example,

|                                     |                                                                      |
|-------------------------------------|----------------------------------------------------------------------|
| **glob!:***\<name\>*                | *refers to a variable with global scope that will be saved on disk.* |
| **@set** *\<name\>***=***\<value\>* | *sets the named variable to the specified value*                     |
| **@set** *\<name\>*                 | *deletes the named variable*                                         |

If you have buttons or status bar codes which react to variable changes, you may need to run the special **@toggle:update** command to make them update their appearances after making changes to variables. See the **@toggle** documentation, below.
</td></tr><tr><td>
@showif</td><td>

The button will be shown if a command clause test is false. This is similar to the conditional testing offered by the **@if** modifier.

|                              |                                                                  |
|------------------------------|------------------------------------------------------------------|
| **@showif:Set DUAL=toggle**  | *button will be shown if the Lister is in dual-display mode*     |
| **@showif:!Set DUAL=toggle** | *button will be shown if the Lister is NOT in dual-display mode* |
</td></tr><tr><td>
@sendkey</td><td>

Sends the specified keystroke to the system. The key will be routed to whichever window currently has focus. For example, `@sendkey:win+v` sends the <kbd>Win</kbd>+<kbd>V</kbd> key to the system, which opens the Windows clipboard viewer.

Supported qualifier keys are `shift`, `ctrl`, `alt` and `win`.

As well as letters and numbers, the following named keys are also supported: `backspace`, `capslock`, `delete`, `down`, `end`, `enter`, `escape`, `home`, `insert`, `left`, `numlock`, `pagedown`, `pageup`, `pause`, `printscr`, `right`, `scrlock`, `space`, `tab`, `up`.
</td></tr><tr><td>

@showifpath  
@showifpathr</td><td>

The button will be shown if the current source path doesn't match the specified pattern. You can provide either an absolute path to test against, or a wildcard pattern (use **@showifpath** for [standard wildcards](../wildcard_reference/pattern_matching_syntax.md), and **@showifpathr** for [regular expressions](../wildcard_reference/regular_expression_syntax.md)).

|                              |                                                                  |
|------------------------------|------------------------------------------------------------------|
| **@showifpathr:^C:\\**       | *show command if source path is on the C: drive*                 |
| **@showifpath:!\*\Work\\**\* | *show unless source path is underneath a folder called **Work*** |

Paths may use aliases, environment variables, {apppath} codes, and so on, only when using wildcards (not regular expressions):

|                                        |                                                                |
|----------------------------------------|----------------------------------------------------------------|
| **@showifpath:!/desktop**              | *show unless in the Desktop folder*                            |
| **@showifpath:!%SystemRoot%\System32** | *show unless in **C:\Windows\System32** (on a typical system)* |
| **@showifpath:{apppath\|dopus.exe}**   | *show if in the folder where Opus is installed*                |
</td></tr><tr><td>
@sync</td><td>

The command following this modifier will be run synchronously - Opus will wait for it to exit before running the next command in the function (or before running this command again for the next selected file).

The default behaviour is for a function that consists of a single command to run that command asynchronously for each selected file; a function that consists of multiple commands will run each command synchronously. The default behaviour can be changed with the **function_default_async** option on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences, or it can be overridden on a per-command basis with this modifier.

|                           |                              |
|---------------------------|------------------------------|
| **@sync:notepad.exe {f}** | *runs Notepad synchronously* |
</td></tr><tr><td>
@toggle</td><td>

For buttons that indicate or change state (e.g. **Set VIEW=details**), this modifier lets you change when the button appears highlighted.

Depending on where the button is displayed, the highlight may appear as a checkmark (e.g. in a text-only menu), or as the icon or label background being drawn in a different color or style (similar to when the button is pushed).

Taking the **Set VIEW=details** command as an example, ordinarily the button would appear highlighted when the file display was in details mode, and not highlighted when it was in any other mode. The **@toggle** modifier can change this:

|                     |                                                           |
|---------------------|-----------------------------------------------------------|
| **@toggle:invert**  | *inverts the usual highlight state of the toolbar button* |
| **@toggle:disable** | *prevents the button from ever appearing highlighted*     |

The @**toggle** modifier can also control when a button appears highlighted by testing a command, similar to the way **@if** and **@ifset** test commands to decide what to run**.** You can use this to highlight a button based on a command which is different to, or in addition to, the commands which the button actually runs.

For example, this button with no **@toggle** line will switch you to *Details* mode when clicked, and will appear highlighted when you are in *Details* mode as well:

    Set VIEW=Details

When **@toggle** is not given, the highlighting (if any) is based on the first command in the button.

Using **@toggle** you can do things like run one **Set** command while testing for another. As a simple, somewhat contrived example, the button below switches to *Details* mode when clicked but appears highlighted when in *Power* mode:

    Set VIEW=Details
    @toggle:if Set VIEW=Power

You can make the **@toggle** test in addition to the first command, rather than instead of it, by putting an "&" character after the "if":

    Set VIEW=Details
    Set COLUMNSADD=thumbnail(0,96)
    @toggle:if&Set COLUMNSTOGGLE=thumbnail

Without the **@toggle** line, the button above would be highlighted when the view mode was *Details* (due to the command) and the highlight would not be affected by the *Thumbnail* column (highlighting does not consider the second command). With the **@toggle** line added, the button will only be highlighted if the view mode is set to *Details* and the *Thumbnail* column is present.  
You can omit the "Set" command name from the **@toggle** line; it will assume you mean the **Set** command if no name is specified. However, this allowance is to avoid breaking old buttons and we recommend you always specify the command when making new ones.

You can test for multiple commands at once by separating them with semi-colons. For example, you could leave out the ampersand and still test for both *Details* mode and the *Thumbnail* column using the following directive (and this will work regardless of any other commands in the button, or even as the only line in the button):

    @toggle:if Set VIEW=Details;Set COLUMNSTOGGLE=thumbnail

You can also negate the result of a test with the exclamation mark in front of the **Set** clause. For example, to make the button appear checked in any mode other than Details:

    @toggle:if !Set VIEW=Details

The **@toggle** directive can also test for the existence of a variable (one set via the **@set** directive). For this to work, the directive must be the very first line of the button, and the variable you are testing must have tab, Lister or global scope. You can use this to create your own custom toggle buttons that keep track of their state using scoped variables. For example:

    @toggle:if $glob:TestVar
    @if:$glob:TestVar
    @set glob:TestVar
    @if:else
    @set glob:TestVar=on

This button tests for the existence of a global variable called *TestVar*. If the variable exists, the button will appear highlighted. Clicking the button evaluates the **@ifset:** directives and will reverse the state of the variable: if the variable is set, it will be deleted; otherwise, it will be set. The end result is a button that performs no function except to toggle a variable and its visible state each time it is clicked. (This can be useful if the variable controls other things, such as the behaviors of other commands or scripts, or the visibility of [status bar elements](../status_bar_codes/other_codes.md).)

A button that begins with **@toggle:if** in this way will automatically update its appearance (to reflect a change in the state of the variable) whenever **@set** is used within it. If you use **@set** in a separate button or hotkey to change the variable, you need to force an update of the toggle button's appearance using the special command **@toggle:update**.

For example, if you have one button which highlights based on a variable but does not change that variable:

    @toggle:if $glob:TestVar

And if you have another button which changes that variable but does not highlight based on it, then you will need to add the **@toggle:update** line to ensure the first button's highlight is updated when you click the second button:

    @if:$glob:TestVar
    @set glob:TestVar
    @if:else
    @set glob:TestVar=on
    @if:common
    @toggle:update

The **@toggle:update** command will also force all **status bars** to refresh, in case they are [using variables](../status_bar_codes/other_codes.md) to display or hide information.

You can also use **@toggle:update** to ensure buttons with dynamic labels (via **@label**, above) are updated after changing variables or other details the label depends on. This also ensures toolbar layouts are adjusted if the label widths change.
</td></tr><tr><td>
@useactivelister</td><td>

The function will operate on the active Lister rather than the current source Lister. Normally these will be the same thing, but this could be useful for a hotkey that you want to have operate on whatever Lister window is currently active, without having to make sure that Lister is set to source first.

|                      |                                              |
|----------------------|----------------------------------------------|
| **@useactivelister** | *use active Lister instead of source lister* |
</td></tr></tbody>
</table>

