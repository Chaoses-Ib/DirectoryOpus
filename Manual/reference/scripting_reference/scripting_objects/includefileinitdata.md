# IncludeFileInitData

If an [include file](/Manual/scripting/script_add-ins/include_files.md) implements the optional **[oninitincludefile](../scripting_events/oninitincludefile.md)** event, an **IncludeFileInitData** object is passed to it to let it provide information about itself. This is completely optional; include files still work without this method, but providing it gives you things like a description and copyright information, and minimum version requirements.

| Property Name | Return Type | Description |
| --- | --- | --- |
| copyright | *string* | Lets you provide copyright information for the include file. |
| desc | *string* | Provides a description of the include file. |
| min_version | *string* | Lets you specify a minimum version of Opus that the include file returns. If the current version is less than the specified version the include file will be disabled. You can specify the major version only (e.g. "13"), a major and minor version (e.g. "13.3") or a specific beta version (e.g. "13.3.1" for 13.3 Beta 1). |
| name | *string* | Provides a display name for the include file. |
| shared | *bool* | If the include file is inside a [script package](/Manual/scripting/script_add-ins/script_package.md), setting this property to **True** makes the include file available to scripts outside that package. If set to **False** only scripts in the same package can include it. |
| url | *string* | Provides a URL which you might, for example, use to link to more information about the include file. |
| version | *string* | Lets you provide a version number for your include file. |

