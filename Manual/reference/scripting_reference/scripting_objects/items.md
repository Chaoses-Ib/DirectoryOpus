# Items

The **Items** object lets you enumerate a collection of one or more **[Item](item.md)** objects. An **Items** object is retrieved from a number of methods and properties, including **[Dialog](dialog.md).Multi**, **[DOpus](dopus.md).GetClip**, **[Command](command.md).files** and several others.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*collection:***[item](item.md)**</td><td>

Returns a collection of **[item](item.md)** objects that you can enumerate.
</td></tr><tr><td>
result</td><td>

*bool*</td><td>

When this **Items** object comes from the **[Dialog](dialog.md).Multi** method, it includes a **result** property giving the result of the dialog. The collection of items is only valid if **result** returns **True**. If it returns **False** it means the user cancelled the dialog.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
RemoveNested</td><td>

*none*</td><td>

*int*</td><td>
Removes any nested items from the collection (items that came from sub-folders rather than the root folder). The number of items removed is returned.
</td></tr><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

Updates the state of this object. This only applies to collections that come from certain sources (e.g. from a **[Tab](tab.md)**). When the **Items** object is first retrieved, a snapshot is taken. Changes made after that outside of the script will not be detected unless you call the **Update** method.
</td></tr></tbody>
</table>

