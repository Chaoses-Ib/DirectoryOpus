# Vector

The **Vector** object is provided to address some short-comings in ActiveX scripting's array support. Some languages have better support than others for arrays, but the languages aren't consistent and some (like *JScript*) have incompatible arrays that Opus is unable to access at all. Therefore, any Opus scripting objects that take or return an array-like variable will use (or prefer to use) a **Vector** rather than an array.

A **Vector** object is mostly able to be used as a straight drop-in replacement for an arrays. They are *collections* and so can be enumerated, or accessed via index (e.g. **Vector(4)** to access the fifth element).  They also have a number of helper methods to make manipulating them easier than arrays often are.

Note that in *JScript* you can access an element using square brackets (just like an array) or parentheses (as if it was a function parameter). In other languages, like *VBScript*, you can only use parentheses.

You can create a new **Vector** using the **[DOpusFactory](dopusfactory.md).Vector** method.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
capacity</td><td>

*int*</td><td>

Returns the capacity of the **Vector** (the number of elements it can hold without having to reallocate memory). This is not the same as the number of elements it currently holds, which can be 0 even if the capacity is something larger.
</td></tr><tr><td>
count</td><td>

*int*</td><td>

Returns the number of elements the **Vector** currently holds.
</td></tr><tr><td>
empty</td><td>

*bool*</td><td>

Returns **True** if the **Vector** is empty, **False** if not.
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
append</td><td>

\<**Vector**:from\>  
\<int:start\>  
\<int:end\></td><td>

*none*</td><td>

Copies the values of another **Vector** to the end of this one, preserving the existing values as well. If *start* and *end* are not provided, the entire **Vector** is appended - otherwise, only the specified elements are appended.

Instead of a **Vector** object you can also pass a *collection* to this method and the contents of the collection will be copied to the end of the **Vector**.  
In *JScript* you can pass a standard array to this method to copy the array to the end of a **Vector**.
</td></tr><tr><td>
assign</td><td>

\<**Vector**:from\>  
\<int:start\>  
\<int:end\></td><td>

*none*</td><td>

Copies the value of another **Vector** to this one. If *start* and *end* are not provided, the entire **Vector** is copied - otherwise, only the specified elements are copied.

Instead of a **Vector** object you can also pass a *collection* to this method and the contents of the collection will be copied to the **Vector**.

In *JScript* you can pass a standard array to this method to copy the array into a **Vector**.
</td></tr><tr><td>
back</td><td>

*none*</td><td>

*variant*</td><td>

Returns the last element in the **Vector**.
</td></tr><tr><td>
clear</td><td>

*none*</td><td>

*none*</td><td>

Clears the contents of the **Vector**.
</td></tr><tr><td>
erase</td><td>
\<int:index\></td><td>

*none*</td><td>
Erases the element at the specified index.
</td></tr><tr><td>
exchange</td><td>
\<int:index1\>  
\<int:index2\></td><td>

*none*</td><td>
Exchanges the positions of the two specified elements.
</td></tr><tr><td>
front</td><td>

*none*</td><td>

*variant*</td><td>

Returns the first element in the **Vector**.
</td></tr><tr><td>
insert</td><td>
\<int:index\>  
\<variant:value\></td><td>

*none*</td><td>
Inserts the provided value at the specified position.
</td></tr><tr><td>
pop_back</td><td>

*none*</td><td>

*none*</td><td>

Removes the last element of the **Vector**.
</td></tr><tr><td>
push_back</td><td>
\<variant:value\></td><td>

*none*</td><td>

Adds the provided value to the end of the **Vector**.
</td></tr><tr><td>
reserve</td><td>
\<int:capacity\></td><td>

*none*</td><td>

Reserves space in the **Vector** for the specified number of elements (increases its **capacity**, although the **count** of elements remains unchanged).

Note that **Vectors** grow dynamically - you don't have to specifically reserve or resize them. However if you want to add a large number of elements to a **Vector** it can be more efficient to reserve space for them first.
</td></tr><tr><td>
resize</td><td>
\<int:size\></td><td>

*none*</td><td>

Resizes the **Vector** to the specified number of elements. Any existing elements past the new size of the **Vector** will be erased.
</td></tr><tr><td>
reverse</td><td>

*none*</td><td>

*none*</td><td>

Reverses the order of the elements held by the **Vector**.
</td></tr><tr><td>
shrink_to_fit</td><td>

*none*</td><td>

*none*</td><td>

Reduces the capacity of the **Vector** to the number of elements it currently holds.
</td></tr><tr><td>
sort</td><td>

*none*</td><td>

*none*</td><td>

Sorts the contents of the **Vector**. Strings and numbers are sorted alphabetically and numerically - other elements are grouped by type but not specifically sorted in any particular order.
</td></tr><tr><td>
unique</td><td>

*none*</td><td>

*int*</td><td>

Removes all but one of any duplicate elements from the **Vector**. The number of elements removed is returned.
</td></tr></tbody>
</table>

