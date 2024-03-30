# DOpusFactory

The **DOpusFactory** object is a helper object that you can use to create various other objects. Unlike the objects that represent existing *things* (e.g. **[Lister](lister.md)** or **[Tab](tab.md)**), the objects created by **DOpusFactory** are independent objects that you can instantiate whenever you need their functionality. The **DOpusFactory** object is obtained via the **[DOpus](dopus.md).Create** method.

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Blob</td><td>

*none*  
or \<int:size\>  
or \<nobr\>\<byte, byte, ...\>\</nobr\>  
or \<**[Blob](blob.md)**:source\></td><td>

*object:***[Blob](blob.md)**</td><td>

Returns a new **[Blob](blob.md)** object, that lets you access and manipulate a chunk of binary data from a script. If no parameters are given the new **Blob** will be empty - you can set its size using the **resize** method - otherwise you can specify the initial size as a parameter.

You can also create a **Blob** pre-filled with data by specifying the actual byte values (e.g. *Blob(72,69,76,76,79)*).

If another **Blob** (or an array - see the documentation on the **Blob** object for a discussion of this) is given then the new **Blob** will be created as a copy of the existing one.
</td></tr><tr><td>
BusyIndicator</td><td>

*none*</td><td>

*object:***[BusyIndicator](busyindicator.md)**</td><td>

Creates a new **[BusyIndicator](busyindicator.md)** object, that lets you control the breadcrumbs bar busy indicator from your script.
</td></tr><tr><td>
Command</td><td>

*none*</td><td>

*object:***[Command](command.md)**</td><td>

Creates a new **[Command](command.md)** object, that lets you run Opus commands from a script.
</td></tr><tr><td>
Date</td><td>

*none*  
or \<variant:date\>  
or *JScript Date*</td><td>

*object*:**[Date](date.md)**</td><td>

Creates a new **[Date](date.md)** object. If a date value is provided the new object will be initialized to that value, otherwise the date will be set to the current local time. The provided value can be one of the following:

- Another **Date** object
- A string in the form "yyyymmdd"
- A string in the form "yyyy-mm-dd hh:mm:ss.mmm" (or part thereof)
- A JScript **Date** object
- A unix epoch time value (seconds since 1/1/1970).
</td></tr><tr><td>
Filter</td><td>

*none*  
or \<string\></td><td>

*object:***[Filter](filter.md)**</td><td>

Creates a new **[Filter](filter.md)** object, which lets you control recursive filtering when running commands from scripts. You can optionally provide a [textual filter](/Manual/file_operations/filtered_operations/textual_filters.md) string to initialise the filter with. Check the **valid** property of the new **Filter** object to find out whether this string was parsed successfully or not.
</td></tr><tr><td>
Map</td><td>

*none*  
or \<variant:key\>,  
\<variant:value\>...</td><td>

*object*:**[Map](map.md)**</td><td>

Creates a new **[Map](map.md)** object. If no arguments are provided, the **Map** will be empty. Otherwise, the **Map** will be pre-initialized with the supplied key/value pairs.

//For <example://>

    Map("firstname","fred","lastname","bloggs");

The individual keys and values can be different types.
</td></tr><tr><td>
StringSet</td><td>

*none*  
or \<string\>, ...</td><td>

*object*:**[StringSet](stringset.md)**</td><td>

Creates a new case-sensitive **[StringSet](stringset.md)** object. If no arguments are provided, the **StringSet** will be empty. Otherwise it will be pre-initialized with the supplied strings; for example:

    StringSet("dog","cat","pony");

You can also pass an array of strings or **[Vector](vector.md)** object to initialise the set.
</td></tr><tr><td>
StringSetI</td><td>

*none*  
or \<string\>, ...</td><td>

*object*:**[StringSet](stringset.md)**</td><td>

Creates a new case-insensitive **[StringSet](stringset.md)** object. If no arguments are provided, the **StringSet** will be empty. Otherwise it will be pre-initialized with the supplied strings.
</td></tr><tr><td>
StringTools</td><td>

*none*</td><td>

*object*:**[StringTools](stringtools.md)**</td><td>

Creates a new **[StringTools](stringtools.md)** object, that provides helper functions for string encoding and decoding.
</td></tr><tr><td>
UnorderedSet</td><td>

*none*  
or *variants*...</td><td>

object:**[UnorderedSet](unorderedset.md)**</td><td>

Creates a new **[UnorderedSet](unorderedset.md)** object. If no arguments are provided the **UnorderedSet** will be empty. Otherwise it will be pre-initialized with the supplied elements.

You can also pass an array or **[Vector](vector.md)** to initialise the set.
</td></tr><tr><td>
Vector</td><td>

*none*  
or \<int:elements\>  
or *variants...*  
or *object:***[vector](vector.md)**  
or *JScript Array*</td><td>

*object:***[Vector](vector.md)**</td><td>

Creates a new **[Vector](vector.md)** object.

If no arguments are provided, the **Vector** will be empty.

If a single integer argument is provided, the **Vector** will be pre-initialized to that number of elements.

You can also pass another **[Vector](vector.md)** or a *JScript* array, or most enumerable objects, as the argument to initialise the new **Vector** with the contents of an existing collection.

If more than one argument is provided, the **Vector** will be pre-initialized with those elements; for example:

    Vector("dog","cat","horse");

The individual elements can be different types.

If you want to create a **Vector** with just a single element, it is best to create an empty **Vector** and then add the element as a second step. Passing a single element during creation can have unexpected results, as it may be interpreted as one of the other cases. (Many of the scripting objects can be implicitly converted into integers or collections.)
</td></tr></tbody>
</table>

