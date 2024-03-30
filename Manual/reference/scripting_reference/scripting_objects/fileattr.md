# FileAttr

The **FileAttr** object is provided to make it easier to deal with file attributes. Rather than dealing with attributes as a string of characters, or a number, it provides properties for each attribute that can be set or queried independently. You can create a new **FileAttr** object using the **[FSUtil](fsutil.md).NewFileAttr** method. **FileAttr** objects are also returned by properties of the **[Format](format.md)** and **[Item](item.md)** objects.

Each attribute is represented by two properties; a single character (e.g. **a**) and its full name (e.g. **archive**). Each property returns **True** if the attribute is set, and **False** if not. For **FileAttr** objects you create yourself, you can also set the value of these properties (and then, for example, apply the attributes to a file using the **[File](file.md).SetAttr** method).

  

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>

Returns a string representing the attributes that are set (similar to the format displayed in the *Attr* column in the file display).
</td></tr><tr><td>

a  
archive</td><td>

*bool*</td><td>
A file or directory that has changes which need archiving. The A bit is usually set on new or modifies files, and may then be cleared by backup software after it has added the changes to a backup.
</td></tr><tr><td>

c  
compressed</td><td>

*bool*</td><td>
A file or directory that is compressed. For a file, all of the data in the file is compressed. For a directory, compression is the default for newly created files and subdirectories.
</td></tr><tr><td>

e  
encrypted</td><td>

*bool*</td><td>
A file or directory that is encrypted. For a file, all data streams in the file are encrypted. For a directory, encryption is the default for newly created files and subdirectories.
</td></tr><tr><td>

h  
hidden</td><td>

*bool*</td><td>
The file or directory is hidden. It is not included in an ordinary directory listing.
</td></tr><tr><td>

i  
nonindexed</td><td>

*bool*</td><td>
The file or directory is not to be indexed by the content indexing service.
</td></tr><tr><td>

o  
offline</td><td>

*bool*</td><td>
The data of a file is not available immediately. This attribute indicates that the file data is physically moved to offline storage. This attribute is used by Remote Storage, which is the hierarchical storage management software. Applications should not arbitrarily change this attribute.
</td></tr><tr><td>

p  
pinned</td><td>

*bool*</td><td>
The data of the file is to be kept available at all times; it should not be offloaded to offline storage.
</td></tr><tr><td>

r  
readonly</td><td>

*bool*</td><td>
A file that is read-only. Applications can read the file, but cannot write to it or delete it. This attribute is not honored on directories.
</td></tr><tr><td>

s  
system</td><td>

*bool*</td><td>
A file or directory that the operating system uses a part of, or uses exclusively.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Assign</td><td>

*object:***FileAttr\\** or *string*</td><td>
none</td><td>

Assigns a new set of attributes to this object. You can pass another **FileAttr** object, or a string (e.g. *"hsr"*).
</td></tr><tr><td>
AttrName</td><td>

*string*</td><td>

*string*</td><td>

Given a single character representing an attribute (e.g. *"a"*) this method returns the name of the attribute in the user's current language (e.g. *"Archive"*).
</td></tr><tr><td>
Clear</td><td>

*object:***FileAttr\\** or *string*</td><td>
none</td><td>

Clears (turns off) the specified attributes in this object. You can pass another **FileAttr** object, or a string representing the attributes to turn off.
</td></tr><tr><td>
Set</td><td>

*object:***FileAttr\\** or *string*</td><td>
none</td><td>

Sets (turns on) the specified attributes in this object. You can pass another **FileAttr** object, or a string representing the attributes to turn on.
</td></tr><tr><td>
ToString</td><td>
none</td><td>
none</td><td>

Returns a string representing the attributes that are set (similar to the format displayed in the *Attr* column in the file display).
</td></tr></tbody>
</table>

  
