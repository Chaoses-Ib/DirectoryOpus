# Creating your own buttons

One of the unique features of Opus is that the toolbars are completely configurable. All toolbar (and menu) buttons are built up from one or more commands, consisting of either:

- The [internal commands](/Manual/reference/command_reference/internal_commands/RAEDME.md), which give access to the internal features of Opus. All the internal commands have a set of [arguments](/Manual/customize/creating_your_own_buttons/internal_command_arguments.md) that can be used to modify their behavior to produce different results (e.g. to move a file instead of copy it).
- External commands, which let you run third-party programs from within Opus. Using [special codes](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md) you can pass information like the names of selected files to external programs, integrating them more fully into your Opus configuration.

Toolbar buttons can also be written as a script using an ActiveX scripting language like VBScript or JScript. See the page on [Scripting](/Manual/scripting/RAEDME.md) for more detail on script buttons.

A few points which may not be immediately apparent:

- Toolbar buttons and drop-down menus are the same thing. A drop-down menu is really just vertical toolbar.
- All the toolbar buttons and menus that come with Opus can be changed. You can edit the supplied buttons (move them around, delete them, modify their function, etc), and add your own buttons (either to the standard toolbars, or to toolbars that you create). You can even turn off the standard toolbars altogether.

- If you ever want to return to the default toolbars, just right-click any toolbar and choose the Reset to Defaults command.

And the most important thing to remember about Opus is:

***If you don't like something, you can probably change it!***

There are many aspects to button and toolbar editing, explained in detail in the pages within this section. To get started, see the list below, or expand this section within the Contents tab on the left.

More:

[Editing the Toolbar](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/RAEDME.md)  
[Command Editor](/Manual/customize/creating_your_own_buttons/command_editor/RAEDME.md)  
[User-defined commands](/Manual/customize/creating_your_own_buttons/user-defined_commands.md)  
[Synchronous and Asynchronous functions](/Manual/customize/creating_your_own_buttons/synchronous_and_asynchronous_functions.md)  
[Internal Command Arguments](/Manual/customize/creating_your_own_buttons/internal_command_arguments.md)  
[Passing files to external programs](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md)  
[Command modifiers](/Manual/customize/creating_your_own_buttons/command_modifiers.md)  
[MS-DOS Batch commands](/Manual/customize/creating_your_own_buttons/ms-dos_batch_commands.md)  
[Embedding Rename Scripts](/Manual/customize/creating_your_own_buttons/embedding_rename_scripts.md)  
[DDE Functions](/Manual/customize/creating_your_own_buttons/dde_functions.md)  
[Embedded functions](/Manual/customize/creating_your_own_buttons/embedded_functions.md)  
