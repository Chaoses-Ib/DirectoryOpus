# OnClick

The **OnClick** event is the main entry point for a [script function](/Manual/scripting/script_functions.md).

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnClick
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[ClickData](../scripting_objects/clickdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

This method is called whenever a button or hotkey containing a [script function](/Manual/scripting/script_functions.md)is run. The **ClickData** object provides useful information about the command environment, including source and destination tabs and paths, any selected files, command line arguments, any qualifier keys that were held down, etc. This information is all accessible from the **ClickData.func** property (which returns a **[Func](../scripting_objects/func.md)** object).  
Note that when a script function is run, any instructions not contained inside a function are executed first, before **OnClick** is invoked. This means that the **OnClick** method is technically optional (as you could just implement the entire script outside of a function), although it is recommended that you implement it simply for the benefit of the **ClickData** object it receives.
</td></tr></tbody>
</table>

