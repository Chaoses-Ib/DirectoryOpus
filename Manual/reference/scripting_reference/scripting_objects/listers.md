# Listers

The **Listers** object is a collection of all currently open [Listers](/Manual/basic_concepts/the_lister/RAEDME.md). It can be obtained via the **[DOpus](dopus.md).listers** property.

**Note:** If you are looking for a window to use as the parent for a **Dialog**, you are probably looking in the wrong place. Scripts should not assume that **DOpus.listers(0)** or **DOpus.listers.lastactive** are the lister which launched them. Most scripting events provide you an object which can either create a pre-configured **Dialog** for you or which includes a **SourceTab** property or similar which can do the same. In almost all situations you should use those instead.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *collection:***[Lister](lister.md)** | Lets you enumerate the currently open Listers.<br /><br />Do not assume that **DOpus.listers(0)** is the window which launched your script. See the note near the top of the page. |
| lastactive | *object:***[Lister](lister.md)** | Returns a **[Lister](lister.md)**object representing the most recently active Lister window.<br /><br />Do not assume that **DOpus.listers.lastactive** is the window which launched your script. See the note near the top of the page. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| ToFront | \<lister\>  <br />\[\<lister\>...\] | *none* | Moves one or more Lister windows to the front. This method accepts one or more arguments; each argument can either be a **[Lister](lister.md)** object or a **[Vector](vector.md)** of **[lister](lister.md)** objects. The last window will placed on top, and all others will be below that in reverse order. |
| Update | *none* | *none* | The first time a script accesses the **DOpus.listers** property, a snapshot is taken of all currently open Listers. If the script then opens or closes Listers itself, these changes will not be reflected by this collection. To re-synchronize the collection, call the **Update** method. |

