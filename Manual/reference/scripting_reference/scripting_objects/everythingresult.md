# EverythingResult

Represents a single item returned in the result set from an Everything query. A [Vector](vector.md) of these objects is returned by a call to the **[EverythingInterface](everythinginterface.md).Query** method.

When you send a query to everything you can tell it what information to return. Only information you request will appear in the result items, so e.g. if you want the file size, you must request it when you send the query.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

access  
access_utc</td><td>

*date*</td><td>
Returns the last access date (in local and UTC time) of the result item. The last access date must have been requested in the query.
</td></tr><tr><td>

create  
create_utc</td><td>

*date*</td><td>
Returns the creation date (in local and UTC time) of the result item. The creation date must have been requested in the query.
</td></tr><tr><td>

daterecentlychanged  
daterecentlychanged_utc</td><td>

*date*</td><td>
Returns the recently changed date (in local and UTC time) of the result item. The value must have been requested in the query.
</td></tr><tr><td>

daterun  
daterun_utc</td><td>

*date*</td><td>
Returns the last run date (in local and UTC time) of the result item. The value must have been requested in the query.
</td></tr><tr><td>
filelist_filename</td><td>

*string*</td><td>
Returns the file list filename of the result item. The value must have been requested in the query.
</td></tr><tr><td>
fullpath</td><td>

*object*:**[Path](path.md)**</td><td>
Returns the full path and name of the result item. The full path and name (or the path and name separately) must have been requested in the query.
</td></tr><tr><td>
highlighted_fullpath</td><td>

*string*</td><td>
Returns the highlighted full path and name of the result item, if the value was requested in the query.
</td></tr><tr><td>
highlighted_name</td><td>

*string*</td><td>
Returns the highlighted name of the result item, if the value was requested in the query.
</td></tr><tr><td>
highlighted_path</td><td>

*string*</td><td>
Returns the highlighted path of the result item, if the value was requested in the query.
</td></tr><tr><td>
name</td><td>

*string*</td><td>
Returns the name of the result item. The name (or full path and name) must have been requested in the query.
</td></tr><tr><td>
path</td><td>

*object*:**[Path](path.md)**</td><td>
Returns the path of the result item. The path (or full path and name) must have been requested in the query.
</td></tr><tr><td>
runcount</td><td>

*int*</td><td>
Returns the item's run count, if it was requested in the query.
</td></tr><tr><td>
size</td><td>

*object*:**[FileSize](filesize.md)**</td><td>
Returns the size of the result item, if it was requested in the query.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
GetItem</td><td>

*none*</td><td>

*object*:**[Item](item.md)**</td><td>

Constructs an Opus [Item](item.md) object representing this result. The full path and filename must have been returned in the result set for this function to work.
</td></tr></tbody>
</table>

