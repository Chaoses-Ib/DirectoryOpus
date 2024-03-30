# Listers

The **Listers** object is a collection of all currently open [Listers](/Manual/basic_concepts/the_lister/README.md). It can be obtained via the **[DOpus](dopus.md).listers** property.

**Note:** If you are looking for a window to use as the parent for a **Dialog**, you are probably looking in the wrong place. Scripts should not assume that **DOpus.listers(0)** or **DOpus.listers.lastactive** are the lister which launched them. Most scripting events provide you an object which can either create a pre-configured **Dialog** for you or which includes a **SourceTab** property or similar which can do the same. In almost all situations you should use those instead.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*collection:***[Lister](lister.md)**</td><td>

Lets you enumerate the currently open Listers.

Do not assume that **DOpus.listers(0)** is the window which launched your script. See the note near the top of the page.
</td></tr><tr><td>
lastactive</td><td>

*object:***[Lister](lister.md)**</td><td>

Returns a **[Lister](lister.md)**object representing the most recently active Lister window.

Do not assume that **DOpus.listers.lastactive** is the window which launched your script. See the note near the top of the page.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
ToFront</td><td>

\<lister\>  
\[\<lister\>...\]</td><td>

*none*</td><td>

Moves one or more Lister windows to the front. This method accepts one or more arguments; each argument can either be a **[Lister](lister.md)** object or a **[Vector](vector.md)** of **[lister](lister.md)** objects. The last window will placed on top, and all others will be below that in reverse order.
</td></tr><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

The first time a script accesses the **DOpus.listers** property, a snapshot is taken of all currently open Listers. If the script then opens or closes Listers itself, these changes will not be reflected by this collection. To re-synchronize the collection, call the **Update** method.
</td></tr></tbody>
</table>

