# Simple Script Function

This is an example of a [script function](../script_functions.md) that displays the name of the largest file in the current folder, and gives you the option to select it.

To use this function you would:

- [Create a new toolbar button](/Manual/customize/creating_your_own_buttons/README.md) or hotkey and [edit](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/README.md) it
- Click the **Advanced** button in the [command editor](/Manual/customize/creating_your_own_buttons/command_editor/README.md) to switch to the [advanced command editor](/Manual/customize/creating_your_own_buttons/command_editor/advanced_command_editor.md)
- Set the **Function** drop-down to **Script Function**

    // Set the script type to JScript to use this script.
    // main script entry point. clickData is a ClickData object.
    function OnClick(clickData)
    {
        // Initialise a variable to keep track of the largest file.
        largestFile = null;

        // Create an enumerator object that will let us easily enumerate the files in the current tab.
        // clickData.func is a Func object.
        // func.sourcetab is a Tab object.
        // sourcetab.files is a collection of Item objects.
        enumFiles = new Enumerator(clickData.func.sourcetab.files);

        // Enumerate the files in the tab.
        enumFiles.moveFirst();
        while (enumFiles.atEnd() == false)
        {
            // If this is the largest file encountered so far, keep track of it.
            // The file size is obtained from the Item object via its size property.
            // We use the FileSize object's cy property as this makes it easier to compare
            // two sizes numerically.
            if (largestFile == null || largestFile.size.cy < enumFiles.item().size.cy)
                largestFile = enumFiles.item();
            enumFiles.moveNext();
        }

        // Create a Dialog object to display the results.
        dlg = clickData.func.Dlg;
        if (largestFile == null)
        {
            // There were no files found, so show a warning message.
            dlg.message = "There are no files in this folder!";
            dlg.buttons = "OK";
            dlg.icon = "warn";
        }
        else
        {
            // Build the info message to report on the largest file.
            // The dialog will have two buttons, giving the user the option to select the file.
            dlg.message = "The largest file is '" + largestFile.name + "' - " + largestFile.size.fmt;
            dlg.buttons = "Select It|Cancel";
            dlg.icon = "info";
        }

        dlg.title = "Largest File Finder";
        
        // Display the dialog. if the user clicks the "Select It" button it will return 1.
        if (dlg.Show() == 1)
        {
            // Initialise and run the Select command to select the largest file.
            // This makes use of the Command object provided to the button via clickData.func.
            clickData.func.command.ClearFiles();
            clickData.func.command.AddFile(largestFile);
            clickData.func.command.RunCommand("Select FROMSCRIPT DESELECTNOMATCH MAKEVISIBLE");
        }
        else
        {
            // Not selecting a file, so make sure anything already selected is unaffected.
            clickData.func.command.deselect = false;
        }
    }
