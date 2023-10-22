# Items

The **Items** object lets you enumerate a collection of one or more **[Item](item.md)** objects. An **Items** object is retrieved from a number of methods and properties, including **[Dialog](dialog.md).Multi**, **[DOpus](dopus.md).GetClip**, **[Command](command.md).files** and several others.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *collection:***[item](item.md)** | Returns a collection of **[item](item.md)** objects that you can enumerate. |
| result | *bool* | When this **Items** object comes from the **[Dialog](dialog.md).Multi** method, it includes a **result** property giving the result of the dialog. The collection of items is only valid if **result** returns **True**. If it returns **False** it means the user cancelled the dialog. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| RemoveNested | *none* | *int* | Removes any nested items from the collection (items that came from sub-folders rather than the root folder). The number of items removed is returned. |
| Update | *none* | *none* | Updates the state of this object. This only applies to collections that come from certain sources (e.g. from a **[Tab](tab.md)**). When the **Items** object is first retrieved, a snapshot is taken. Changes made after that outside of the script will not be detected unless you call the **Update** method. |

