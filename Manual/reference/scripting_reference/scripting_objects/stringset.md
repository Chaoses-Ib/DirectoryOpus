# StringSet

The **StringSet** object is container that stores one or more unique strings. It is similar to an array or vector (e.g. **[Vector](vector.md)**) but has the advantage of using a dictionary system to locate strings rather than numeric indexes. You can therefore lookup strings much more quickly than by linearly searching a **[Vector](vector.md)**.

You can create a new **StringSet** using the **[DOpusFactory](dopusfactory.md)**object. A **StringSet** can be either case-sensitive ("cat" and "CAT" would be treated as two different strings) or case-insensitive.

| Property Name | Return Type | Description |
| --- | --- | --- |
| count | *int* | Returns the number of elements the **StringSet** currently holds. |
| empty | *bool* | Returns **True** if the **StringSet** is empty, **False** if not. |
| length | *int* | A synonym for **count**. |
| size | *int* | A synonym for **count**. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| assign | \<**StringSet**:from\> | *none* | Copies the contents of another **StringSet** to this one. You can also pass an array of strings or **[Vector](vector.md)** object. |
| clear | *none* | *none* | Clears the contents of the **StringSet**. |
| erase | \<string\> | *none* | Erases the string if it exists in the set. |
| exists | \<string\> | *bool* | Returns **True** if the specified string exists in the set. |
| insert | \<string\> | *bool* | Inserts the string into the set if it doesn't already exist. Returns **True** if successful. |
| merge | \<**StringSet**:from\> | *none* | Merges the contents of another **StringSet** with this one. |

