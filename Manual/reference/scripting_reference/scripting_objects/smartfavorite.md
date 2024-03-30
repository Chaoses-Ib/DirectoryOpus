# SmartFavorite

A **SmartFavorite** object represents an entry for a folder in the [SmartFavorites](/Manual/basic_concepts/the_lister/navigation/smartfavorites.md) table. It is retrieved by enumerating or indexing the **[SmartFavorites](smartfavorites.md)** object.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
path</td><td>

*object:***[Path](path.md)**</td><td>

Returns the path this entry represents, as a **[Path](path.md)** object.
</td></tr><tr><td>
points</td><td>

*int*</td><td>
Returns the number of points this entry has as a source folder. The point score is used by Opus to determine which folders to display.
</td></tr><tr><td>
destpoints</td><td>

*int*</td><td>
Returns the number of points this entry has as a destination folder.
</td></tr></tbody>
</table>

