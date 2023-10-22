# UnorderedSet

The **UnorderedSet** object is container that stores one or more unique objects. It is similar to a StringSet except it can store variants of any type (rather than just strings), and the contents are not kept sorted (in fact, the order of set members is unspecified). Like a StringSet it uses a dictionary system to locate members rather than numeric indexes. You can therefore lookup members much more quickly than by linearly searching a **[Vector](vector.md)**.

You can create a new **UnorderedSet** using the **[DOpusFactory](dopusfactory.md)**object.

Care should be taken when adding objects to an **UnorderedSet**. Unlike strings and numbers, the container will only consider two objects equal if both are the exact same object (i.e. same instance/reference). Two separate objects with the same value will not be considered equal, and can both exist in the same **UnorderedSet** at once.

##### JScript Example:

    var us = DOpus.Create.UnorderedSet();

    us.insert("cat");
    us.insert("cat"); // No effect, as "cat" already inserted.
    us.insert("dog");
    us.insert(DOpus.FSUtil.NewPath("C:\\"));
    us.insert(DOpus.FSUtil.NewPath("C:\\")); // Inserts a second C:\ Path object!

    var p = DOpus.FSUtil.NewPath("D:\\");
    us.insert(p);
    us.insert(p); // No effect, as p already inserted.

    DOpus.Output("count: " + us.count);

    for (var e = new Enumerator(us); !e.atEnd(); e.moveNext())
    {
    DOpus.Output("Item: " + e.item());
    }

That will output the following (order of items may vary):

    count: 5
    Item: cat
    Item: dog
    Item: D:\
    Item: C:\
    Item: C:\

| Property Name | Return Type | Description |
| --- | --- | --- |
| count | *int* | Returns the number of elements the **UnorderedSet** currently holds. |
| empty | *bool* | Returns **True** if the **UnorderedSet** is empty, **False** if not. |
| length | *int* | A synonym for **count**. |
| size | *int* | A synonym for **count**. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| assign | \<**UnorderedSet**:from\> | *none* | Copies the contents of another **UnorderedSet** to this one. You can also pass an array or **[Vector](vector.md)** object. |
| clear | *none* | *none* | Clears the contents of the **UnorderedSet**. |
| erase | *variant* | *none* | Erases the element if it exists in the set. |
| exists | *variant\\* | *bool* | Returns **True** if the specified element exists in the set. |
| insert | *variant* | *bool* | Inserts the element into the set if it doesn't already exist. Returns **True** if successful. |
| merge | \<**UnorderedSet**:from\> | *none* | Merges the contents of another **UnorderedSet** with this one. |

