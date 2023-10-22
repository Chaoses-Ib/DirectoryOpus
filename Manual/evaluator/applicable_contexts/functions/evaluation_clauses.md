# Evaluation Clauses in Functions

The **@eval** and **@evalalways** [command modifiers](/Manual/reference/command_reference/command_modifier_reference.md) let you run evaluation expressions inline in your functions.

The main purpose of this is to set variables that can then be used later on in the function by other modifiers like **@if**, **@icon**, **@label** etc.

- Variables set via **@eval** can only be seen by other modifiers. They're executed when Opus performs dynamic updates of the toolbar (e.g. to update the label or icon), but not when the function is actually run.
- Variables set by **@evalalways** can also been seen by the main function itself, when it is run. That means they can also be accessed via [evaluation insertion code](insertion_code.md) or by generated [command lines](commands.md).

For example, you might want a button that behaves differently in a normal filesystem folder to other locations. You can use an **@eval** clause to calculate the folder type once, and then refer to that in later lines.

    @eval:=type = pathtype(source); fIsFileSystem = (type == "shell" || type == "filesys")
    @enableif:=fIsFileSystem
    @label:=fIsFileSystem ? ("Open " + filepart(displayname(source)) + " in Explorer") : ("Disabled (" + type + ")")
    explorer.exe "{sourcepath}"

![](page>standard_variables&nodate&nouser&nofooter)

The return value from the evaluation expression will be used to determine the result of the condition. Return **true** if the lines following the modifier should be executed, or **false** to skip to the next **@if** / **@ifset** modifier.
