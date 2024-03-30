# StringSet

The **StringSet** object is container that stores one or more unique strings. It is similar to an array or vector (e.g. **[Vector](vector.md)**) but has the advantage of using a dictionary system to locate strings rather than numeric indexes. You can therefore lookup strings much more quickly than by linearly searching a **[Vector](vector.md)**.

You can create a new **StringSet** using the **[DOpusFactory](dopusfactory.md)**object. A **StringSet** can be either case-sensitive ("cat" and "CAT" would be treated as two different strings) or case-insensitive.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>

Returns the number of elements the **StringSet** currently holds.
</td></tr><tr><td>
empty</td><td>

*bool*</td><td>

Returns **True** if the **StringSet** is empty, **False** if not.
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

\<**StringSet**:from\></td><td>

*none*</td><td>

Copies the contents of another **StringSet** to this one. You can also pass an array of strings or **[Vector](vector.md)** object.
</td></tr><tr><td>
clear</td><td>

*none*</td><td>

*none*</td><td>

Clears the contents of the **StringSet**.
</td></tr><tr><td>
erase</td><td>
\<string\></td><td>

*none*</td><td>
Erases the string if it exists in the set.
</td></tr><tr><td>
exists</td><td>
\<string\></td><td>

*bool*</td><td>

Returns **True** if the specified string exists in the set.
</td></tr><tr><td>
insert</td><td>
\<string\></td><td>

*bool*</td><td>

Inserts the string into the set if it doesn't already exist. Returns **True** if successful.
</td></tr><tr><td>
merge</td><td>

\<**StringSet**:from\></td><td>

*none*</td><td>

Merges the contents of another **StringSet** with this one.
</td></tr></tbody>
</table>

