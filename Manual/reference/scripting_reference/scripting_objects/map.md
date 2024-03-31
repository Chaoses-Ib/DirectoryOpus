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

### JScript Example:

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

### VBScript Example:

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

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>

Returns the number of elements the **Map** currently holds.
</td></tr><tr><td>
empty</td><td>

*bool*</td><td>

Returns **True** if the **Map** is empty, **False** if not.
</td></tr><tr><td>
length</td><td>

*int*</td><td>

A synonym for **count**.
</td></tr><tr><td>
size</td><td>

*int*</td><td>

A synonym for **count**.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
assign</td><td>

\<**Map**:from\></td><td>

*none*</td><td>

Copies the contents of another **Map** to this one.
</td></tr><tr><td>
clear</td><td>

*none*</td><td>

*none*</td><td>

Clears the contents of the **Map**.
</td></tr><tr><td>
erase</td><td>

\<variant:key\></td><td>

*none*</td><td>
Erases the element matching the specified key, if it exists in the map.
</td></tr><tr><td>
exists</td><td>

\<variant:key\></td><td>

*bool*</td><td>

Returns **True** if the specified key exists in the map.
</td></tr><tr><td>
get</td><td>

\<variant:key\></td><td>

*variant*</td><td>
Returns the value of the specified key.
</td></tr><tr><td>
merge</td><td>

\<**Map**:from\></td><td>

*none*</td><td>

Merges the contents of another **Map** with this one.
</td></tr><tr><td>
set</td><td>

\<variant:key\>  
\<variant:value\></td><td>

*none*</td><td>
Sets the value of the specified key.
</td></tr></tbody>
</table>

