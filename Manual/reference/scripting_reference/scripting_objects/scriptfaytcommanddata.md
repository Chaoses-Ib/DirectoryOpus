# ScriptFAYTCommandData

The **ScriptFAYTCommandData** object is passed to the script-defined entry points for any [script add-ins](/Manual/scripting/script_add-ins/README.md) that [extend the FAYT field](/Manual/scripting/example_scripts/extending_the_fayt.md). The method name for these events is defined by the script itself, but generically it's referred to as **[onscriptfaytcommand](../scripting_events/onscriptfaytcommand.md)**.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
cmdline</td><td>

*string*</td><td>
Provides the text the user typed into the FAYT field.
</td></tr><tr><td>
fayt</td><td>

*string*  
or *bool*</td><td>

The name of the FAYT extension command being invoked. This lets you use the same entry point to implement multiple FAYT extensions if desired. If the value is **False** then this is not a FAYT extension at all, but a regular [script command](scriptcommanddata.md).
</td></tr><tr><td>
flags</td><td>

*int*</td><td>

Provides the sum of all the flags the user has enabled for your FAYT extension. These come from the **flags** property you specified when initialising your extension via the **[scriptfaytcommand](scriptfaytcommand.md)** object.

Your script can update the flags in the users' configuration using the **[Script](script.md).UpdateFAYTFlags** method.
</td></tr><tr><td>
key</td><td>

*string*</td><td>

This will equal the string **"return"** if the user pushed the return key to trigger your FAYT extension.
</td></tr><tr><td>
suggest</td><td>

*bool*</td><td>

If set to **True** this is a hint that you should update the suggestions list via the **[tab](tab.md).UpdateFAYTSuggestions** method.
</td></tr><tr><td>
quickkey</td><td>

*string*</td><td>
Provides the key that initially triggered the FAYT in this mode.
</td></tr><tr><td>
tab</td><td>

*object:***[tab](tab.md)**</td><td>
Represents the tab in which the FAYT is being interacted with.
</td></tr></tbody>
</table>

