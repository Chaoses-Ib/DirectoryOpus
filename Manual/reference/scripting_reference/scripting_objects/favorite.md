# Favorite

A **Favorite** object represents a [favorite folder](/Manual/basic_concepts/the_lister/navigation/favorites.md). It is retrieved by enumerating or indexing the [Favorites](favorites.md)object.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns the name of the favorite folder or sub-folder. |
| folder | *bool* | Returns **True** if this is a sub-folder, **False** if it's a favorite folder or separator.<br /><br />If this object is a sub-folder it also behaves like a **[Favorites](favorites.md)** object as well as a **Favorite** object, and can be enumerated and have elements added and removed from it. |
| separator | *bool* | Returns **True** if this is a separator. |
| path | *object:***[Path](path.md)** | Returns the path this favorite folder refers to as a **[Path](path.md)** object. |

| Method// Name// | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| SetHeading | \<string:heading\> | *none* | If this is a separator (i.e. the **separator** property returns **True**) this lets you make the separator into a heading, or change the heading text.<br /><br />Note that changes you make to the list are not saved until you call the **[Favorites](favorites.md).Save** method. |
| SetName | \<string:name\> | *none* | Changes the name of this favorite folder. Note that changes you make to the list are not saved until you call the **[Favorites](favorites.md).Save** method. |
| SetPath | \<string:path\> or  <br />\<object:**[Path](path.md)**\> | *none* | Changes the path this favorite folder refers to. Note that changes you make to the list are not saved until you call the **[Favorites](favorites.md).Save** method. |

