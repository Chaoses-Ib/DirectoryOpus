# Adding a new Internal Command

This is an example of a [script add-in](../script_add-ins/README.md) that adds a new internal command to Opus.

This command, **SelectNewest**, selects one or more of the newest files in the current folder. You would use this by creating a new **.js** file in the *Script Addins* folder (type **/dopusdata/Script Addins** into the location field to find this).

You could then create a button or hotkey to run the **SelectNewest** command just like any other internal Opus command.

The basic procedure to add an internal command from a [script add-in](../script_add-ins/README.md) is:

- Either:
  - In the **[OnInit](/Manual/reference/scripting_reference/scripting_events/oninit.md)** event, create a **[ScriptCommand](/Manual/reference/scripting_reference/scripting_objects/scriptcommand.md)** object with the **[ScriptInitData](/Manual/reference/scripting_reference/scripting_objects/scriptinitdata.md).AddCommand** method.
  - Or, in the **[OnAddCommands](/Manual/reference/scripting_reference/scripting_events/onaddcommands.md)** event, create a **[ScriptCommand](/Manual/reference/scripting_reference/scripting_objects/scriptcommand.md)** object with the **[AddCmdData](/Manual/reference/scripting_reference/scripting_objects/addcmddata.md).AddCommand** method.

- Initialize the properties of the **[ScriptCommand](/Manual/reference/scripting_reference/scripting_objects/scriptcommand.md)** object. At a minimum you must populate the **name** and **method** properties.
- Create a separate function in your script-add in, with the **method** name you specified for the command. This will be your command's entry point.

    // Set the script type to JScript to use this script
    // The **OnInit**function is called by Directory Opus to initialize the script add-in
    function OnInit(initData) {
    // Provide basic information about the script by initializing the properties of the **ScriptInitData**object
    initData.name = "Select Newest Files";
    initData.desc = "Select the newest X files in the folder";
    initData.copyright = "(c) 2016 Jonathan Potter";
    initData.default_enable = true;
    // Create a new **ScriptCommand**object and initialize it to add the command to Opus
    var cmd = initData.AddCommand();
    cmd.name = "SelectNewest";
    cmd.method = "OnSelectNewest";
    cmd.desc = initData.desc;
    cmd.label = "Select Newest Files";
    cmd.template = "NUMBER/N,FROM/K/N,NODESELECT/S";
    }
    // Implement the SelectNewest command (this entry point is an **OnScriptCommand**event).
    // The name of this function must correspond to the value specified for the **method **property when the command was added in **OnInit**
    function OnSelectNewest(scriptCmdData) {
    // **scriptCmdData** is a **ScriptCommandData**object, and it provides the raw command-line and a **Func**object.
    // The **Func** object contains an **Args**object, which in turn contains our parsed arguments (if any), usually preferable to using the raw command-line.
    // we use the **got_arg** object to test if an argument was provided, before reading its value
    // First get the starting index to select from, from the **FROM** argument. Default to 0 (newest) if not supplied.
    iStartPos = 0;
    if ( scriptCmdData.func.args.got_arg.from ) iStartPos = scriptCmdData.func.args.from;

    // Next get the number of files to select, from the **NUMBER** argument. Default to 1 if not supplied
    iNumber = 1;
    if ( scriptCmdData.func.args.got_arg.number ) iNumber = scriptCmdData.func.args.number;

    // The **func.sourcetab** property returns a **Tab**object representing the function's source tab
    // We create an enumerator for files in the source tab (**sourcetab.files**).
    // To change this to operate on files and folders rather than just files, use **sourcetab.all **instead

    var objEnum = new Enumerator( scriptCmdData.func.sourcetab.files );

    // build an Array of the files so we can sort it
    var objFiles = new Array();
    i = 0;
    while (!objEnum.atEnd()) {
    objFiles[i++] = objEnum.item();
    objEnum.moveNext();
    }

    if (objFiles.length > 0) {

    // Sort the array by the "modify" property. This will sort the file array
    // in order from newest to oldest
    objFiles.sort(function(a, b) {
    if (a.modify < b.modify)
    return 1;
    if (a.modify > b.modify)
    return -1;
    return 0;
    });
    // By default we get given a **Command**object pre-filled for the current tab
    // we can use that instead of creating our own, but we need to clear
    // out its list of files if it has one already
    scriptCmdData.func.command.ClearFiles();

    // Starting from the specified start position, add the requested number
    // of files to the command object. Because we have sorted the array from newest
    // to oldest, this will automatically add the newest files to the command
    for ( i = iStartPos; i < objFiles.length && i < iStartPos + iNumber; i++ ) {
    scriptCmdData.func.command.AddFile( objFiles[i] );
    }

    // Build the Select command line to run that will actually select the files.
    // The FROMSCRIPT argument is needed to select files from the command object.
    // The DESELECTNOMATCH argument is used to deselect all other files, unless the
    // script's NODESELECT argument was used.

    strCommand = "Select FROMSCRIPT";
    if (!scriptCmdData.func.args.got_arg.nodeselect)
    strCommand += " DESELECTNOMATCH";
    // run the Select command via the **Command**object's **RunCommand** method
    scriptCmdData.func.command.RunCommand( strCommand );
    }
    }

  
