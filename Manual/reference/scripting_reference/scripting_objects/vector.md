# Vector

The **Vector** object is provided to address some short-comings in ActiveX scripting's array support. Some languages have better support than others for arrays, but the languages aren't consistent and some (like *JScript*) have incompatible arrays that Opus is unable to access at all. Therefore, any Opus scripting objects that take or return an array-like variable will use (or prefer to use) a **Vector** rather than an array.

A **Vector** object is mostly able to be used as a straight drop-in replacement for an arrays. They are *collections* and so can be enumerated, or accessed via index (e.g. **Vector(4)** to access the fifth element).  They also have a number of helper methods to make manipulating them easier than arrays often are.

Note that in *JScript* you can access an element using square brackets (just like an array) or parentheses (as if it was a function parameter). In other languages, like *VBScript*, you can only use parentheses.

You can create a new **Vector** using the **[DOpusFactory](dopusfactory.md).Vector** method.

| Property Name | Return Type | Description |
| --- | --- | --- |
| capacity | *int* | Returns the capacity of the **Vector** (the number of elements it can hold without having to reallocate memory). This is not the same as the number of elements it currently holds, which can be 0 even if the capacity is something larger. |
| count | *int* | Returns the number of elements the **Vector** currently holds. |
| empty | *bool* | Returns **True** if the **Vector** is empty, **False** if not. |
| length | *int* | A synonym for **count**. |
| size | *int* | A synonym for **count**. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| append | \<**Vector**:from\>  <br />\<int:start\>  <br />\<int:end\> | *none* | Copies the values of another **Vector** to the end of this one, preserving the existing values as well. If *start* and *end* are not provided, the entire **Vector** is appended - otherwise, only the specified elements are appended.<br /><br />Instead of a **Vector** object you can also pass a *collection* to this method and the contents of the collection will be copied to the end of the **Vector**.  <br />In *JScript* you can pass a standard array to this method to copy the array to the end of a **Vector**. |
| assign | \<**Vector**:from\>  <br />\<int:start\>  <br />\<int:end\> | *none* | Copies the value of another **Vector** to this one. If *start* and *end* are not provided, the entire **Vector** is copied - otherwise, only the specified elements are copied.<br /><br />Instead of a **Vector** object you can also pass a *collection* to this method and the contents of the collection will be copied to the **Vector**.<br /><br />In *JScript* you can pass a standard array to this method to copy the array into a **Vector**. |
| back | *none* | *variant* | Returns the last element in the **Vector**. |
| clear | *none* | *none* | Clears the contents of the **Vector**. |
| erase | \<int:index\> | *none* | Erases the element at the specified index. |
| exchange | \<int:index1\>  <br />\<int:index2\> | *none* | Exchanges the positions of the two specified elements. |
| front | *none* | *variant* | Returns the first element in the **Vector**. |
| insert | \<int:index\>  <br />\<variant:value\> | *none* | Inserts the provided value at the specified position. |
| pop_back | *none* | *none* | Removes the last element of the **Vector**. |
| push_back | \<variant:value\> | *none* | Adds the provided value to the end of the **Vector**. |
| reserve | \<int:capacity\> | *none* | Reserves space in the **Vector** for the specified number of elements (increases its **capacity**, although the **count** of elements remains unchanged).<br /><br />Note that **Vectors** grow dynamically - you don't have to specifically reserve or resize them. However if you want to add a large number of elements to a **Vector** it can be more efficient to reserve space for them first. |
| resize | \<int:size\> | *none* | Resizes the **Vector** to the specified number of elements. Any existing elements past the new size of the **Vector** will be erased. |
| reverse | *none* | *none* | Reverses the order of the elements held by the **Vector**. |
| shrink_to_fit | *none* | *none* | Reduces the capacity of the **Vector** to the number of elements it currently holds. |
| sort | *none* | *none* | Sorts the contents of the **Vector**. Strings and numbers are sorted alphabetically and numerically - other elements are grouped by type but not specifically sorted in any particular order. |
| unique | *none* | *int* | Removes all but one of any duplicate elements from the **Vector**. The number of elements removed is returned. |

