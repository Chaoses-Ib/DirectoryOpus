# ScriptInitData

The **ScriptInitData** object is passed to the **[OnInit](../scripting_events/oninit.md)** event in a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md). The script should initialize the various properties to identify itself, and can optionally [add internal commands](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) using the **AddCommand** method, and [custom columns](/Manual/scripting/example_scripts/adding_a_new_column.md) using the **AddColumn** method, before returning.

| Property Name | Return Type | Description |
| --- | --- | --- |
| config | *object:***[ScriptConfig](scriptconfig.md)** | Returns a **[ScriptConfig](scriptconfig.md)** object, that the script can use to initialize its default configuration. Properties added to the object in this method will be displayed to the user in Preferences, allowing them to change their value and thus configure the behavior of the script. |
| config_desc | *object:***[Map](map.md)** | This lets you assign descriptions for your script's configuration options that are shown to the user in the editor dialog. To do this, set this property to a **[Map](map.md)** created via the **[DOpusFactory](dopusfactory.md).Map** method, filled with name/description string pairs. |
| config_groups | *object:***[Map](map.md)** | This lets you organize your script's configuration options into groups when shown to the user in the editor dialog. The group names are arbitrary - configuration options with the same group name will appear grouped together. Set this property to a **[Map](map.md)** created via the **[DOpusFactory](dopusfactory.md).Map** method, filled with name/group string pairs. |
| copyright | *string* | Lets the script specify a copyright message that is displayed to the user in Preferences. |
| default_enable | *bool* | Set this to **True** if the script should be enabled by default, or **False** if it should be disabled by default. The user can enable or disable scripts using Preferences - this simply controls the default state. |
| desc | *string* | Lets the script specify a description message that is displayed to the user in Preferences. |
| early_dblclk | *bool* | Set this to **True** if your script implements the **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event and (for performance reasons) you want to be called with only a path to the double-clicked item rather than a full **[Item](item.md)** object. See the **[OnDoubleClick](../scripting_events/ondoubleclick.md)** event documentation for more details. |
| file | *string* | Returns the path and filename of this script. |
| group | *string* | Lets you specify an arbitrary group for this script. If scripts specify a group they will be displayed in that group in the list in Preferences. |
| log_prefix | string | Lets the script specify a string that will be prepended to any log output it performs. If not set the name of the script is used by default. |
| min_version | *string* | Specifies the minimum Opus version required. If the current version is less than the specified version the script will be disabled. You can specify the major version only (e.g. *"11"*), a major and minor version (e.g. *"11.3"*) or a specific beta version (e.g. *"11.3.1"* for 11.3 Beta 1). |
| name | *string* | Lets the script specify a display name for the script that is shown in Preferences. |
| startup | *bool* | The **OnInit** method is called in two different circumstances - once during Opus startup, and again if the script is installed or edited when Opus is already running. This property will return **True** if the **OnInit** method is being called during Opus startup, or **False** for any other time. |
| url | *string* | Lets you provide a URL where the user can go to find out more about your script (it's displayed to the user in Preferences). |
| vars | *object:***[Vars](vars.md)** | Returns a **[Vars](vars.md)** collection of user and script-defined variables that are local to this script. These variables are available to other methods in the script via the **[Script](script.md).vars** property. |
| version | *string* | Lets the script specify a version number string that is displayed to the user in Preferences. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| AddColumn | *none* | *object:***[ScriptColumn](scriptcolumn.md)** | Adds a new information column to Opus. The returned **[ScriptColumn](scriptcolumn.md)** object must be properly initialized. A script add-in can add as many columns as it likes, and these will be available in file displays, infotips and the **[Advanced Find](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/RAEDME.md)** function.<br /><br />Instead of adding columns in **OnInit**, your script can implement the **[OnAddColumns](../scripting_events/onaddcolumns.md)** method. This is more flexible as it allows you to access your script's configuration at the time you add columns, and columns can be dynamically added and removed while Opus is running. If **[OnAddColumns](../scripting_events/onaddcolumns.md)** is implemented then this method is unavailable in **OnInit**. |
| AddCommand | *none* | *object:***[ScriptCommand](scriptcommand.md)** | Adds a new internal command to Opus. The returned **[ScriptCommand](scriptcommand.md)** object must be properly initialized. A script add-in can add as many internal commands as it likes to the Opus internal command set.<br /><br />Instead of adding commands in **OnInit**, your script can implement the **[OnAddCommands](../scripting_events/onaddcommands.md)** method. This is more flexible as it allows you to access your script's configuration at the time you add commands, and commands can be dynamically added and removed while Opus is running. If **[OnAddCommands](../scripting_events/onaddcommands.md)** is implemented then this method is unavailable in **OnInit**. |
