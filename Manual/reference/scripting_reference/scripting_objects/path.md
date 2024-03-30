# Path

The **Path** object represents a file or folder path. Many objects have properties that return a **Path** - for example, **[Tab](tab.md).path** returns the current folder in a tab as a **Path** object. You can create a new **Path** object from a string (or another **Path**) using the **[DOpus](dopus.md).**[FSUtil](fsutil.md)**.NewPath** method.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>
Returns the full path as a string.
</td></tr><tr><td>
components</td><td>

*int*</td><td>
Returns the number of components in the path.
</td></tr><tr><td>
disks</td><td>

**[Vector](vector.md)***:int*</td><td>

Returns a **[Vector](vector.md)**of *ints* representing the physical disk drive or drives that this path resides on.
</td></tr><tr><td>
drive</td><td>

*int*</td><td>
Returns the drive number the path refers to (1=A, 2=B, etc.) or 0 if the path does not specify a drive. You can also change the drive letter of the path (while leaving the following path components alone) by modifying this value.
</td></tr><tr><td>
ext</td><td>

*string*</td><td>

Returns the filename extension of the path (the sub-string extending from the last **.** in the final component to the end of the string). This method does not check if the path actually refers to a file.

You can also change a path's file extension by setting this property (and strip the extension altogether by setting it to an empty string).
</td></tr><tr><td>
ext_m</td><td>

*string*</td><td>

Returns the filename extension of the path, taking multi-part extensions into account. For example, **ext** might return ".rar" whereas **ext_m** would return ".part1.rar".

You can't change the extension using **ext_m**, only **ext**.
</td></tr><tr><td>
filepart</td><td>

*string*</td><td>
Returns the filename part of the path (the last component).
</td></tr><tr><td>
longpath</td><td>

*object:***Path**</td><td>
If this object represents a short pathname, this property returns the "long" equivalent.
</td></tr><tr><td>
pathpart</td><td>

*string*</td><td>
Returns the path minus the last component.
</td></tr><tr><td>
shortpath</td><td>

*object:***Path**</td><td>
If this object represents a long pathname, this property returns the "short" equivalent, if it has one. Note that short paths are disabled by default in Windows 10.
</td></tr><tr><td>
stem</td><td>

*string*</td><td>

Returns the filename stem of the path (i.e. **filepart** minus **ext**).
</td></tr><tr><td>
stem_m</td><td>

*string*</td><td>

Returns the filename stem taking multi-part extensions into account. For example, **stem** might return "pictures.part1" whereas **stem_m** would return "pictures".
</td></tr><tr><td>
test_parent</td><td>

*bool*</td><td>

Returns **True** if a call to the **Parent** method would succeed.
</td></tr><tr><td>
test_root</td><td>

*bool*</td><td>

Returns **True** if a call to the **Root** method would succeed.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Add</td><td>

\<string:name\>  
or \<**[Vector](vector.md)***:string\>*</td><td>

*none*</td><td>

Adds the specified name to the path (it will become the last component). As well as a string, you can pass a **[Vector](vector.md)** of strings and all items in the vector will be added to the path.
</td></tr><tr><td>
Normalize</td><td>

*none*</td><td>

*none*</td><td>

Normalizes the path by:

- Converting all forward-slashes to back-slashes (or vice versa for a URL)
- Collapsing duplicate slashes to a single slash (except where needed)

**Normalize** is automatically called when a new path string is assigned to a **Path** object so you don't normally need to call it manually.
</td></tr><tr><td>
Parent</td><td>

*none*</td><td>

*bool*</td><td>

Removes the last component of the path. Returns **False** if the path does not have a valid parent.
</td></tr><tr><td>
ReplaceStart</td><td>
\<string:old\>  
\<string:new\>  
\<bool:wholepath\></td><td>

*bool*</td><td>

Compares the beginning of the path with the "old" string, and if it matches replaces it with the "new" string. The match is performed at the path component level - for example, an "old" string of "C:\Foo" would match the path "C:\Foo\Bar" but not "C:\FooBar". If the optional *wholepath* argument is set to **True** then the whole path must match rather than just its beginning. Returns **True** if the string matched the path or **False** otherwise.
</td></tr><tr><td>
Resolve</td><td>
\<string:flags\></td><td>

*none*</td><td>

Resolves the specified path string to its real filesystem path, with support for converting:

- **[Folder Aliases](/Manual/basic_concepts/the_lister/navigation/aliases.md)** to the real paths they point to.
- **Library** and **File Collection** items to their real filesystem paths.
- Application paths in the **{apppath\|*appname*}** form.
- Environment variables.
- Optionally, **junctions** and **symbolic links** can be resolved to their targets. The **Path** object is modified in-place.

It is safe to pass a path which does not need resolving; the path will remain as-is, so you can call this on things without checking if it is needed first.

Scripts which pass the current directory to external software should generally call Resolve on the path first, otherwise they risk passing aliases like */desktop* to things which won't understand them.

The optional **flags** string can include the following letter (not case-sensitive):

|       |                                                                 |
|-------|-----------------------------------------------------------------|
| **j** | resolve **j**unctions and symbolic links to their target folder |

Note that **[DOpus](dopus.md).[FSUtil](fsutil.md)** has a similar **Resolve** method which takes a string input and returns a new **Path** object.
</td></tr><tr><td>
Root</td><td>

*none*</td><td>

*bool*</td><td>

Strips off all but the first component of the path. Returns **False** if the path is already at the root.
</td></tr><tr><td>
Set</td><td>

\<string:path\>  
or \<**Path**:path\>  
or \<**[Vector](vector.md)***:string\>*</td><td>

*none*</td><td>

Sets the path represented by the **Path** object to the specified *string*.

You can also set one **Path** object to the value of another. If you pass a **[Vector](vector.md)** of strings the path will be built from the items in the vector.
</td></tr><tr><td>
Split</td><td>
\<int:first\>  
\<int:count\></td><td>

**[Vector](vector.md)***:string*</td><td>

Returns a **[Vector](vector.md)** of strings representing the components of the path. For example, if the path is **C:\Foo\Bar**, the vector will contain three items - "C:\\, "Foo" and "Bar". By default all components of the path are returned, but you can optionally provide the index of the first component and also the number of components to return.
</td></tr><tr><td>
ToUNC</td><td>

*none*</td><td>

*bool*</td><td>

If the path begins with the drive letter of a mapped network drive, it will be converted into the UNC version of the path. For example, "X:\Test" may map to "\\Server\Share\Test". Returns **True** if the path was modified and **False** if it was not.
</td></tr></tbody>
</table>

