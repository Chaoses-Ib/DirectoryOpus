# Favorite

A **Favorite** object represents a [favorite folder](/Manual/basic_concepts/the_lister/navigation/favorites.md). It is retrieved by enumerating or indexing the [Favorites](favorites.md)object.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>
Returns the name of the favorite folder or sub-folder.
</td></tr><tr><td>
folder</td><td>

*bool*</td><td>

Returns **True** if this is a sub-folder, **False** if it's a favorite folder or separator.

If this object is a sub-folder it also behaves like a **[Favorites](favorites.md)** object as well as a **Favorite** object, and can be enumerated and have elements added and removed from it.
</td></tr><tr><td>
separator</td><td>

*bool*</td><td>

Returns **True** if this is a separator.
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.md)**</td><td>

Returns the path this favorite folder refers to as a **[Path](path.md)** object.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method// Name//</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
SetHeading</td><td>
\<string:heading\></td><td>

*none*</td><td>

If this is a separator (i.e. the **separator** property returns **True**) this lets you make the separator into a heading, or change the heading text.

Note that changes you make to the list are not saved until you call the **[Favorites](favorites.md).Save** method.
</td></tr><tr><td>
SetName</td><td>
\<string:name\></td><td>

*none*</td><td>

Changes the name of this favorite folder. Note that changes you make to the list are not saved until you call the **[Favorites](favorites.md).Save** method.
</td></tr><tr><td>
SetPath</td><td>

\<string:path\> or  
\<object:**[Path](path.md)**\></td><td>

*none*</td><td>

Changes the path this favorite folder refers to. Note that changes you make to the list are not saved until you call the **[Favorites](favorites.md).Save** method.
</td></tr></tbody>
</table>

