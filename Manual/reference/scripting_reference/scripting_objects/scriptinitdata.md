# ScriptInitData

The **ScriptInitData** object is passed to the **[OnInit](../scripting_events/oninit.md)** event in a [script add-in](/Manual/scripting/script_add-ins/README.md). The script should initialize the various properties to identify itself, and can optionally [add internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) using the **AddCommand** method, and [custom columns](/Manual/scripting/example_scripts/adding_a_new_column.md) using the **AddColumn** method, before returning.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
config</td><td>

*object:***[ScriptConfig](scriptconfig.md)**</td><td>

Returns a **[ScriptConfig](scriptconfig.md)** object, that the script can use to initialize its default configuration. Properties added to the object in this method will be displayed to the user in Preferences, allowing them to change their value and thus configure the behavior of the script.
</td></tr><tr><td>
config_desc</td><td>

*object:***[Map](map.md)**</td><td>

This lets you assign descriptions for your script's configuration options that are shown to the user in the editor dialog. To do this, set this property to a **[Map](map.md)** created via the **[DOpusFactory](dopusfactory.md).Map** method, filled with name/description string pairs.
</td></tr><tr><td>
config_groups</td><td>

*object:***[Map](map.md)**</td><td>

This lets you organize your script's configuration options into groups when shown to the user in the editor dialog. The group names are arbitrary - configuration options with the same group name will appear grouped together. Set this property to a **[Map](map.md)** created via the **[DOpusFactory](dopusfactory.md).Map** method, filled with name/group string pairs.
</td></tr><tr><td>
copyright</td><td>

*string*</td><td>
Lets the script specify a copyright message that is displayed to the user in Preferences.
</td></tr><tr><td>
default_enable</td><td>

*bool*</td><td>

Set this to **True** if the script should be enabled by default, or **False** if it should be disabled by default. The user can enable or disable scripts using Preferences - this simply controls the default state.
</td></tr><tr><td>
desc</td><td>

*string*</td><td>
Lets the script specify a description message that is displayed to the user in Preferences.
</td></tr><tr><td>
early_dblclk</td><td>

*bool*</td><td>

Set this to **True** if your script implements the **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event and (for performance reasons) you want to be called with only a path to the double-clicked item rather than a full **[Item](item.md)** object. See the **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event documentation for more details.
</td></tr><tr><td>
file</td><td>

*string*</td><td>
Returns the path and filename of this script.
</td></tr><tr><td>
group</td><td>

*string*</td><td>
Lets you specify an arbitrary group for this script. If scripts specify a group they will be displayed in that group in the list in Preferences.
</td></tr><tr><td>
log_prefix</td><td>
string</td><td>
Lets the script specify a string that will be prepended to any log output it performs. If not set the name of the script is used by default.
</td></tr><tr><td>
min_version</td><td>

*string*</td><td>

Specifies the minimum Opus version required. If the current version is less than the specified version the script will be disabled. You can specify the major version only (e.g. *"11"*), a major and minor version (e.g. *"11.3"*) or a specific beta version (e.g. *"11.3.1"* for 11.3 Beta 1).
</td></tr><tr><td>
name</td><td>

*string*</td><td>
Lets the script specify a display name for the script that is shown in Preferences.
</td></tr><tr><td>
startup</td><td>

*bool*</td><td>

The **OnInit** method is called in two different circumstances - once during Opus startup, and again if the script is installed or edited when Opus is already running. This property will return **True** if the **OnInit** method is being called during Opus startup, or **False** for any other time.
</td></tr><tr><td>
url</td><td>

*string*</td><td>
Lets you provide a URL where the user can go to find out more about your script (it's displayed to the user in Preferences).
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.md)**</td><td>

Returns a **[Vars](vars.md)** collection of user and script-defined variables that are local to this script. These variables are available to other methods in the script via the **[Script](script.md).vars** property.
</td></tr><tr><td>
version</td><td>

*string*</td><td>
Lets the script specify a version number string that is displayed to the user in Preferences.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddColumn</td><td>

*none*</td><td>

*object:***[ScriptColumn](scriptcolumn.md)**</td><td>

Adds a new information column to Opus. The returned **[ScriptColumn](scriptcolumn.md)** object must be properly initialized. A script add-in can add as many columns as it likes, and these will be available in file displays, infotips and the **[Advanced Find](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.md)** function.

Instead of adding columns in **OnInit**, your script can implement the **[OnAddColumns](../scripting_events/onaddcolumns.md)** method. This is more flexible as it allows you to access your script's configuration at the time you add columns, and columns can be dynamically added and removed while Opus is running. If **[OnAddColumns](../scripting_events/onaddcolumns.md)** is implemented then this method is unavailable in **OnInit**.
</td></tr><tr><td>
AddCommand</td><td>

*none*</td><td>

*object:***[ScriptCommand](scriptcommand.md)**</td><td>

Adds a new internal command to Opus. The returned **[ScriptCommand](scriptcommand.md)** object must be properly initialized. A script add-in can add as many internal commands as it likes to the Opus internal command set.

Instead of adding commands in **OnInit**, your script can implement the **[OnAddCommands](../scripting_events/onaddcommands.md)** method. This is more flexible as it allows you to access your script's configuration at the time you add commands, and commands can be dynamically added and removed while Opus is running. If **[OnAddCommands](../scripting_events/onaddcommands.md)** is implemented then this method is unavailable in **OnInit**.
</td></tr></tbody>
</table>

