# Adding a new Column

This is an example of a [script add-in](../script_add-ins/RAEDME.md) that adds a new information column to Opus.

This column, **Is Modified?**, indicates whether a file has been modified since it was created. This is performed by simply comparing whether the item's creation and modification dates are the same.

- For files that have been modified, the column displays *Yes*, and for files that haven't been modified it displays *No*. Nothing is displayed for folders.
- When sorting by this column, modified files are displayed above non-modified files.
- When grouping by this column, the two groups are labeled *Modified* and *Never Modified*.

The basic procedure to add a custom column from a [script add-in](../script_add-ins/RAEDME.md) is:

- Either:
  - In the **[OnInit](/Manual/reference/scripting_reference/scripting_events/oninit.md)** event, create a **[ScriptColumn](/Manual/reference/scripting_reference/scripting_objects/scriptcolumn.md)**object with the **[ScriptInitData](/Manual/reference/scripting_reference/scripting_objects/scriptinitdata.md).AddColumn** method.
  - Or, in the **[OnAddColumns](/Manual/reference/scripting_reference/scripting_events/onaddcolumns.md)** event, create a **[ScriptColumn](/Manual/reference/scripting_reference/scripting_objects/scriptcolumn.md)**object with the **[AddColData](/Manual/reference/scripting_reference/scripting_objects/addcoldata.md).AddColumn** method.

- Initialize the properties of the **[ScriptColumn\*\*](/Manual/reference/scripting_reference/scripting_objects/scriptcolumn.md)**object. At a minimum you must populate the **name** and **method** properties. \* Create a separate function in your script-add in, with the **method** name you specified for the column. This method will be called when Opus wants to retrieve data for your column.

    // Set the script type to JScript to use this script
    // The **OnInit**function is called by Directory Opus to initialize the script add-in
    function OnInit(initData) {

    // Provide basic information about the script by initializing the properties of the **ScriptInitData**object
    initData.name = "Is Modified Column";
    initData.desc = "Adds a column that indicates if a file has ever been modified.";
    initData.copyright = "(c) 2014 Jonathan Potter";
    initData.default_enable = true; // Create a new **ScriptColumn**object and initialize it to add the column to Opus
    var cmd = initData.AddColumn();
    cmd.name = "IsModified";
    cmd.method = "OnIsModified";
    cmd.label = "Is Modified?";
    cmd.autogroup = false; // we provide our own grouping information
    cmd.autorefresh = true; // refresh column when files change
    cmd.justify = "center";
    cmd.match.push_back("Yes"); // when searching, these are the only two options
    cmd.match.push_back("No");
    }

    // Implement the IsModified column (this entry point is an **OnScriptColumn**event).
    // The name of this function must correspond to the value specified for the **method **property when the column was added in **OnInit**
    function OnIsModified(scriptColData) {

    // **scriptColData** is a **ScriptColumnData**object. first check that this is the right column (it should be since we only added one)
    if (scriptColData.col != "IsModified")
    return;
    // we don't provide a value for folders since their timestamps don't mean much
    // we set the sort key to 3 so they come last (in case the user is mixing files and folders)
    if (scriptColData.item.is_dir) {
    scriptColData.value = "";
    scriptColData.sort = 3;
    }
    // for files, are the two dates the same?
    else if (new Date(scriptColData.item.create).valueOf() == new Date(scriptColData.item.modify).valueOf()) {
    scriptColData.value = "No";
    scriptColData.group = "Never Modified";
    scriptColData.sort = 2;
    }
    // the dates are different, therefore modified
    else {
    scriptColData.value = "Yes";
    scriptColData.group = "Modified";
    scriptColData.sort = 1;
    }
    }
