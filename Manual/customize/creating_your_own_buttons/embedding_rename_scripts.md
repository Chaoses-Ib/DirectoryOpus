# Embedding Rename Scripts

[Rename scripts](/Manual/file_operations/renaming_files/advanced_rename/rename_scripts.md) can be embedded directly in a button or hotkey, which lets you rename files using a script without having to display the **[Advanced Rename](/Manual/file_operations/renaming_files/advanced_rename/RAEDME.md)** dialog first.

![](/Manual/images/media/rename_embed.png)

This image depicts an example of an embedded rename script. The first line of such a button must call the **[Rename](/Manual/reference/command_reference/internal_commands/rename.md)** command. This command actually invokes the Rename function - and you can use any of the arguments for the **Rename** command to perform "pre-processing" before the script is invoked. For example, you could use the command **Rename CASE=allwords** to capitalize words in the filename first, before the script is invoked. In the above screenshot the **Rename** command will not actually modify the filename itself - it will be passed through verbatim to the script.

Below the **Rename** command, the **@script** [command modifier](/Manual/reference/command_reference/command_modifier_reference.md) is used to introduce the script. This tells Opus which language the script is written in - **vbscript** is shown in the above screenshot, but you can specify **jscript** to use JavaScript, and other languages are also supported if you have them installed.

Any text in the function definition below the **@script** line defines the script itself. See the [Rename Scripts](/Manual/scripting/rename_scripts/RAEDME.md) page for more information on writing rename scripts.
