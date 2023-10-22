# Version

The **Version** object is retrieved from the **[DOpus](dopus.md).version **property. It provides information about the current version of Directory Opus.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Full version string (as shown in the *About* dialog). |
| build | *int* | The current build number. |
| module | *string* | The current module version (the version of **dopus.exe** itself). You can also enumerate or index this as a *collection:int* to retrieve the individual four digits of the module version. |
| product | *string* | The current product version (the release version of Directory Opus as a whole). You can also enumerate or index this as a *collection:int* to retrieve the individual four digits of the product version. |
| winver | *object*:**[WinVer](winver.md)** | Returns a **[WinVer](winver.md)** object which provides information about the current version of Windows. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| AtLeast | \<string:version\> | *bool* | Returns **True** if the current version of Opus is the specified version or greater. You can specify the major version only (e.g. *"11"*), a major and minor version (e.g. *"11.3"*) or a specific beta version (e.g. *"11.3.1"*). |

