# Script

The **Script** object is one of the two global script objects provided by Opus. This** **object is provided to [script addins](/Manual/scripting/script_add-ins/README.md) when their various event handlers are invoked (other than for the **[OnInit](../scripting_events/oninit.md)** event). It provides information relating to the script itself.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
config</td><td>

*object:***[ScriptConfig](scriptconfig.md)**</td><td>

Returns a **[ScriptConfig](scriptconfig.md)** object representing the configuration values for this script. In the **[OnInit](../scripting_events/oninit.md)** method a script can define the properties that make up its configuration - the user can then edit these values in Preferences. The object returned by the **config** property represents the values that the user has chosen.
</td></tr><tr><td>
file</td><td>

*string*</td><td>
Returns the path and filename of this script.
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.md)**</td><td>

Returns a **[Vars](vars.md)** object that represents the variables that are scoped to this particular script. This allows scripts to use variables that persist from one invocation of the script to another.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
InitColumns</td><td>

*none*</td><td>

*none*</td><td>

If your script implements the **[OnAddColumns](../scripting_events/onaddcolumns.md)** event, you can call the **InitColumns** method at any time to reinitialize your columns. You may want to do this, for example, in response to the user modifying your script's configuration.
</td></tr><tr><td>
InitCommands</td><td>

*none*</td><td>

*none*</td><td>

If your script implements the **[OnAddCommands](../scripting_events/onaddcommands.md)** event, you can call the **InitCommands** method at any time to reinitialize your commands. You may want to do this, for example, in response to the user modifying your script's configuration.
</td></tr><tr><td>
LoadImage</td><td>

\<string:name\>  
\[\<int:width\>\]  
\[\<int:height\>\]  
\[\<bool:alpha\>\]</td><td>

object:**[Image](image.md)**</td><td>

Loads an image file from the specified external file. If your script is bundled as a [script package](/Manual/scripting/script_add-ins/script_package.md) you can place image files in a sub-directory of the package called **images** and then load them from your script by giving their name. You can optionally specify the desired size to load the image at, and whether the alpha channel (if any) should be loaded or not.

The returned **[Image](image.md)** object can be given as the value of the **[Control](control.md).label** property for a static control in a [script dialog](/Manual/scripting/script_dialogs/README.md) (when that control is in "image" mode). You can also assign as to the **icon** property of a **[Dialog](dialog.md)** object to specify a custom window icon for your script dialog.
</td></tr><tr><td>
LoadResources</td><td>
\<string:name\> or  
\<string:XML\></td><td>

*none*</td><td>

Loads external [script resources](/Manual/scripting/resources/README.md) and makes them available to the script. You can either provide a filename or a raw XML string. If your script is bundled as a [script package](/Manual/scripting/script_add-ins/script_package.md), the resource file must have a **.odxml** extension for **LoadResources** to be able to find it in the package.
</td></tr><tr><td>
RefreshColumn</td><td>
\<string:name\></td><td>

*none*</td><td>
If your script implements any custom columns, you can use this method to cause them to be regenerated if they are currently shown in any tabs. You may want to do this, for example, in response to the user modifying your script's configuration. Pass the name of the column you want to regenerate as the argument to this method.
</td></tr><tr><td>
UpdateFAYTFlags</td><td>
\<string:name\>  
\<int:flags\></td><td>

*none*</td><td>

Lets a script add-in update the flags for a [FAYT extension](/Manual/scripting/example_scripts/extending_the_fayt.md). This equates to the options shown to the user for the FAYT mode on the [Quick Keys](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.md) Preferences page.

The *name* should be the name of the FAYT extension command; this is given to your command as the **[ScriptFAYTCommandData](scriptfaytcommanddata.md).fayt** property. The *flags* value should represent a flag combination that's meaningful to your extension.
</td></tr></tbody>
</table>

