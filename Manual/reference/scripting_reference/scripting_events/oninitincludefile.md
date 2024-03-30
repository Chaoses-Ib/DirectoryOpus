# OnInitIncludeFile

The **OnInitIncludeFile** event is called once for each [include file](/Manual/scripting/script_add-ins/include_files.md) script to initialize it. Implementing this event is optional, but recommended as it allows you to provide a name, description and other information such as minimum version requirements.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnInitIncludeFile
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[IncludeFileInitData](../scripting_objects/includefileinitdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

When Opus starts up, or when an include file script is added or edited, its **OnInitIncludeFile** method is called. This gives the include file a chance to tell Opus something about itself, by setting the various properties of the **IncludeFileInitData** object.
</td></tr></tbody>
</table>

