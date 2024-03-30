# Version

The **Version** object is retrieved from the **[DOpus](dopus.md).version **property. It provides information about the current version of Directory Opus.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>

Full version string (as shown in the *About* dialog).
</td></tr><tr><td>
build</td><td>

*int*</td><td>
The current build number.
</td></tr><tr><td>
module</td><td>

*string*</td><td>

The current module version (the version of **dopus.exe** itself). You can also enumerate or index this as a *collection:int* to retrieve the individual four digits of the module version.
</td></tr><tr><td>
product</td><td>

*string*</td><td>

The current product version (the release version of Directory Opus as a whole). You can also enumerate or index this as a *collection:int* to retrieve the individual four digits of the product version.
</td></tr><tr><td>
winver</td><td>

*object*:**[WinVer](winver.md)**</td><td>

Returns a **[WinVer](winver.md)** object which provides information about the current version of Windows.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AtLeast</td><td>
\<string:version\></td><td>

*bool*</td><td>

Returns **True** if the current version of Opus is the specified version or greater. You can specify the major version only (e.g. *"11"*), a major and minor version (e.g. *"11.3"*) or a specific beta version (e.g. *"11.3.1"*).
</td></tr></tbody>
</table>

