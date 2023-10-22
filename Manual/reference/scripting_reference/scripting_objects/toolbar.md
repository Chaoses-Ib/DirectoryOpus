# Toolbar

The **Toolbar** object represents a toolbar. **Toolbar** objects can represent a specific instance of a toolbar (open in a specific Lister), and can also represent the toolbar itself, on disk, that doesn't have to currently be open at all.

- When retrieved from the **[Toolbars](toolbars.md)** object (which in turn comes from the **[DOpus](dopus.md).Toolbars** method), the object represents a toolbar on disk. You can find out where it is currently in use from its properties.
- When retrieved from the **[Lister](lister.md).toolbars** property, it represents an instance of a toolbar in that particular Lister.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns the name of the toolbar. |
| deftoolbar | *bool* | Returns **True** if this is a default (factory-provided) toolbar, or **False** if it was user-created.  <br />(Old scripts may use "default" instead of "deftoolbar"; this is deprecated because it does not work in JScript where "default" is a reserved keyword.) |
| listers | *collection:***[Lister](lister.md)** | Returns a collection of **[Lister](lister.md)** objects representing any and all Listers this toolbar is currently open in. |
| docks | *collection:***[Dock](dock.md)** | Returns a collection of **[Dock](dock.md)** objects representing any currently floating instances of this toolbar. |
| group | *string* | Returns a *string* indicating the group (position) of a particular instance of this toolbar. The returned string will be one of *top*, *bottom*, *left*, *right*, *center*, *fdright*, *fdbottom*, *tree*. |
| line | *int* | Returns the line number within the toolbar's group that it resides on. For example, the first toolbar at the top of the Lister would have a line of 0. |
| pos | *int* | Returns the pixel position from the left/top of the toolbar's line. If there are two or more toolbars with the same **line** number, the **pos** value determines the order they appear in. |

