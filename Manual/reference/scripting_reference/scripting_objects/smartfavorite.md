# SmartFavorite

A **SmartFavorite** object represents an entry for a folder in the [SmartFavorites](/Manual/basic_concepts/the_lister/navigation/smartfavorites.md) table. It is retrieved by enumerating or indexing the **[SmartFavorites](smartfavorites.md)** object.

| Property Name | Return Type | Description |
| --- | --- | --- |
| path | *object:***[Path](path.md)** | Returns the path this entry represents, as a **[Path](path.md)** object. |
| points | *int* | Returns the number of points this entry has as a source folder. The point score is used by Opus to determine which folders to display. |
| destpoints | *int* | Returns the number of points this entry has as a destination folder. |

