# Toolbars

The **Toolbars** object lets you enumerate all the defined toolbars in your Directory Opus configuration (whether currently turned on or not). It's retrieved using the **[DOpus](dopus.md).Toolbars** method.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*collection:***[Toolbar](toolbar.md)**</td><td>

Returns a collection of **[Toolbar](toolbar.md)** objects that you can enumerate.
</td></tr><tr><td>
fdb</td><td>

*string*  
or  
**[Vector](vector.md):***string*</td><td>

Returns the name(s) of the currently selected File Display Toolbar(s).  
If the FDB toolbar is disabled, returns the string **!static** to indicate a static header.  
If there is only one FDB toolbar configured (the usual case), it is returned as a simple string.  
If more than one FDB toolbar is configured, a **[Vector](vector.md)** of strings is returned.  
You can use **DOpus.toolbars.fdb(0)** in both JScript and VBScript if you just want the name of the first toolbar without worrying about whether the number of other toolbars (if any). Otherwise, use **TypeName(...)** in VBScript and **typeof** in JScript to determine the return type.
</td></tr><tr><td>
viewer</td><td>

*string*</td><td>
Returns the name of the currently selected Viewer Toolbar.
</td></tr></tbody>
</table>

