# Toolbars

The **Toolbars** object lets you enumerate all the defined toolbars in your Directory Opus configuration (whether currently turned on or not). It's retrieved using the **[DOpus](dopus.md).Toolbars** method.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *collection:***[Toolbar](toolbar.md)** | Returns a collection of **[Toolbar](toolbar.md)** objects that you can enumerate. |
| fdb | *string*  <br />or  <br />**[Vector](vector.md):***string* | Returns the name(s) of the currently selected File Display Toolbar(s).  <br />If the FDB toolbar is disabled, returns the string **!static** to indicate a static header.  <br />If there is only one FDB toolbar configured (the usual case), it is returned as a simple string.  <br />If more than one FDB toolbar is configured, a **[Vector](vector.md)** of strings is returned.  <br />You can use **DOpus.toolbars.fdb(0)** in both JScript and VBScript if you just want the name of the first toolbar without worrying about whether the number of other toolbars (if any). Otherwise, use **TypeName(...)** in VBScript and **typeof** in JScript to determine the return type. |
| viewer | *string* | Returns the name of the currently selected Viewer Toolbar. |

