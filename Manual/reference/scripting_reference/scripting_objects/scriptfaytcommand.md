# ScriptFAYTCommand

When a script calls the **[ScriptInitData](scriptinitdata.md).AddCommand** method to [add commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) to the Opus internal command set, the **[scriptcommand](scriptcommand.md)** object it retrieves provides a **ScriptFAYTCommand** object in the **fayt** property. You can initialise this object to create a command that [extends the FAYT field](/Manual/scripting/example_scripts/extending_the_fayt.md).

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
backcolor</td><td>

*string*</td><td>

Specify the default background color for your FAYT extension. This should be in the form **\#RRGGBB** (hexadecimal) or **RRR,GGG,BBB** (decimal). You should use this and the **textcolor** property to specify both dark and light colors as the same, otherwise use the **dark** and **light** properties.
</td></tr><tr><td>
dark</td><td>

*object:***[ScriptColorPair](scriptcolorpair.md)**</td><td>

Use the **[ScriptColorPair](scriptcolorpair.md)** object this returns to specify the default dark mode text and background colors for your FAYT extension (and use the **light** property to specify the light mode colors). If you want the default dark and light colors to be the same, you can use the **textcolor** and **backcolor** properties instead.
</td></tr><tr><td>
enable</td><td>

*bool*</td><td>

Set this property to **True** to enable the FAYT extension.
</td></tr><tr><td>
flags</td><td>

*object:***[Map](map.md)**</td><td>

Lets you specify a set of flags that the user will be able to turn on or off through the user interface. To use this, you need to assign the property to a **[map](map.md)** object created by the **[dopus](dopus.md).[Create](dopusfactory.md).Map** method.

Each flag should be added to the map with its numeric value (a power of two; e.g. 1, 2, 4, 8, ...) as the key and its label as the value. When your FAYT extension is called, Opus will add the values of the flags the user has chosen together and pass them to your command.

The maximum number of flags you can add is 16.
</td></tr><tr><td>
key</td><td>

*string*</td><td>
Lets you specify a default key for your FAYT extension. Pushing this key from a file display or FAYT field will invoke the script.
</td></tr><tr><td>
label</td><td>

*string*</td><td>
This lets you specify a label for your FAYT extension which is shown in the user interface. If not supplied, the name of the command is used.
</td></tr><tr><td>
light</td><td>

*object:***[ScriptColorPair](scriptcolorpair.md)**</td><td>

Use the **[ScriptColorPair](scriptcolorpair.md)** object this returns to specify the default light mode text and background colors for your FAYT extension (and use the **dark** property to specify the dark mode colors). If you want the default dark and light colors to be the same, you can use the **textcolor** and **backcolor** properties instead.
</td></tr><tr><td>
realtime</td><td>

*bool*  
or *int*</td><td>

Set to **True** to have your extension called in realtime as the user types. If set to **False** your extension will be called only when the user presses <kbd>Enter</kbd>. If set to an integer value, this specifies the number of milliseconds between when the user types and your script is called (i.e. deferred notification).
</td></tr><tr><td>
textcolor</td><td>

*string*</td><td>

Specify the default text color for your FAYT extension. This should be in the form **\#RRGGBB** (hexadecimal) or **RRR,GGG,BBB** (decimal). You should use this and the **backcolor** property to specify both dark and light colors as the same, otherwise use the **dark** and **light** properties.
</td></tr><tr><td>
wantempty</td><td>

*bool*</td><td>
Set to false if you don't want to be called for a suggestion list for an empty string (i.e. the user must type something before your extension is invoked).
</td></tr></tbody>
</table>

