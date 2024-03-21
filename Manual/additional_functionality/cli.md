# CLI

The **CLI / Ad-Hoc Script Editor** has two main functions:

- It provides a very simple command line interface (CLI) to the Directory Opus command set.
- In Script mode, it allows you to design and test ad-hoc [scripts](/Manual/scripting/README.md).

You can open the CLI using the **Tools / Opus CLI** menu command.

![](/Manual/images/media/cli.png) 

  
The command line lets you run [internal commands](/Manual/reference/command_reference/internal_commands/README.md) directly without having to configure a button or hotkey first. It is similar to using the [find-as-you-type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field in command mode. You can also display the full template for any internal command by entering the command name followed by a ? symbol (as in the screenshot above).

Turning on the **Script interpreter** option puts the CLI in Script mode, which allows you to design and test ad-hoc scripts. The drop-down field lets you select the script language - if the language you wish to use isn't listed, simply type the name in. You will need to consult the documentation for third-party languages as to the name of the "script engine".

![](/Manual/images/media/cli_scriptmode.png)

Press **F5** or click the **Run** button to run your script. Any errors, warnings or text output from the script (e.g. via the **DOpus.Output** method) will be displayed in output field below the editor.

(Accelerator keys mentioned below are for the English version of Directory Opus. Hover the mouse over buttons to discover their accelerators in your language.)

The **Abort** (**Alt+A**) button can be used to stop a script which is caught in a loop.

The **New** (**Alt+N**) button clears both the script and output field so you can start afresh.

The **Load** (**Alt+L**) and **Save** (**Alt+S**) buttons allow you to load and save scripts for use at a later date.

If the **Clear** option is checked, the output field will be cleared each time a script is run; otherwise, output from each run will accumulate.
