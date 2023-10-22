# Map

The **Map** object is an [associative container](http://en.wikipedia.org/wiki/Associative_container). It is similar to an array or vector (e.g. **[Vector](vector.md)**) in that it can store one or more objects, but has the advantage of using a dictionary system to locate objects rather than numeric indexes. You can therefore insert or lookup objects using an arbitrary value (string, integer, date, etc.) as the key. (Note that keys are implicitly converted into strings, regardless of initial type.)

You can access elements of the map as if the map is a function (e.g. **Map("foo")** to reference an element by the key *"foo"*). You can also use square brackets (like an array or Vector) but only if the name of the key begins with an underscore, or is completely numeric (e.g. **Map\[123\]** or **Map\["\_foo"\]**). Additionally you can use the **get** and **set** methods.

You can create a new **Map** using the **[DOpusFactory](dopusfactory.md).Map** method. The keys in a map can be enumerated, and are automatically kept sorted.

The two examples below both output the following:

    count: 4
    bird -> tweet
    cat -> meow
    dog -> woof
    snake -> hiss

##### JScript Example:

    var map = DOpus.Create.Map();

    map("cat") = "meow";
    map("dog") = "woof";
    map("bird") = "tweet";
    map("snake") = "hiss";

    DOpus.Output("count: " + map.count);

    for (var e = new Enumerator(map); !e.atEnd(); e.moveNext())
    {
     var key = e.item();
     var value = map(key);
     DOpus.Output(key + " -> " + value);
    }

##### VBScript Example:

    Dim map, key, value
    Set map = DOpus.Create.Map

    map("cat") = "meow"
    map("dog") = "woof"
    map("bird") = "tweet"
    map("snake") = "hiss"

    DOpus.Output "count: " & map.count

    For Each key In map
     value = map(key)
     DOpus.Output(key & " -> " & value)
    Next

| Property Name | Return Type | Description |
| --- | --- | --- |
| count | *int* | Returns the number of elements the **Map** currently holds. |
| empty | *bool* | Returns **True** if the **Map** is empty, **False** if not. |
| length | *int* | A synonym for **count**. |
| size | *int* | A synonym for **count**. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| assign | \<**Map**:from\> | *none* | Copies the contents of another **Map** to this one. |
| clear | *none* | *none* | Clears the contents of the **Map**. |
| erase | \<variant:key\> | *none* | Erases the element matching the specified key, if it exists in the map. |
| exists | \<variant:key\> | *bool* | Returns **True** if the specified key exists in the map. |
| get | \<variant:key\> | *variant* | Returns the value of the specified key. |
| merge | \<**Map**:from\> | *none* | Merges the contents of another **Map** with this one. |
| set | \<variant:key\>  <br />\<variant:value\> | *none* | Sets the value of the specified key. |

