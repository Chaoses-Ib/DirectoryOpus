# IncludeFileInitData

If an [include file](/Manual/scripting/script_add-ins/include_files.md) implements the optional **[oninitincludefile](../scripting_events/oninitincludefile.md)** event, an **IncludeFileInitData** object is passed to it to let it provide information about itself. This is completely optional; include files still work without this method, but providing it gives you things like a description and copyright information, and minimum version requirements.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
copyright</td><td>

*string*</td><td>
Lets you provide copyright information for the include file.
</td></tr><tr><td>
desc</td><td>

*string*</td><td>
Provides a description of the include file.
</td></tr><tr><td>
min_version</td><td>

*string*</td><td>
Lets you specify a minimum version of Opus that the include file returns. If the current version is less than the specified version the include file will be disabled. You can specify the major version only (e.g. "13"), a major and minor version (e.g. "13.3") or a specific beta version (e.g. "13.3.1" for 13.3 Beta 1).
</td></tr><tr><td>
name</td><td>

*string*</td><td>
Provides a display name for the include file.
</td></tr><tr><td>
shared</td><td>

*bool*</td><td>

If the include file is inside a [script package](/Manual/scripting/script_add-ins/script_package.md), setting this property to **True** makes the include file available to scripts outside that package. If set to **False** only scripts in the same package can include it.
</td></tr><tr><td>
url</td><td>

*string*</td><td>
Provides a URL which you might, for example, use to link to more information about the include file.
</td></tr><tr><td>
version</td><td>

*string*</td><td>
Lets you provide a version number for your include file.
</td></tr></tbody>
</table>

