# FileAttr

The **FileAttr** object is provided to make it easier to deal with file attributes. Rather than dealing with attributes as a string of characters, or a number, it provides properties for each attribute that can be set or queried independently. You can create a new **FileAttr** object using the **[FSUtil](fsutil.md).NewFileAttr** method. **FileAttr** objects are also returned by properties of the **[Format](format.md)** and **[Item](item.md)** objects.

Each attribute is represented by two properties; a single character (e.g. **a**) and its full name (e.g. **archive**). Each property returns **True** if the attribute is set, and **False** if not. For **FileAttr** objects you create yourself, you can also set the value of these properties (and then, for example, apply the attributes to a file using the **[File](file.md).SetAttr** method).

  

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns a string representing the attributes that are set (similar to the format displayed in the *Attr* column in the file display). |
| a  <br />archive | *bool* | A file or directory that has changes which need archiving. The A bit is usually set on new or modifies files, and may then be cleared by backup software after it has added the changes to a backup. |
| c  <br />compressed | *bool* | A file or directory that is compressed. For a file, all of the data in the file is compressed. For a directory, compression is the default for newly created files and subdirectories. |
| e  <br />encrypted | *bool* | A file or directory that is encrypted. For a file, all data streams in the file are encrypted. For a directory, encryption is the default for newly created files and subdirectories. |
| h  <br />hidden | *bool* | The file or directory is hidden. It is not included in an ordinary directory listing. |
| i  <br />nonindexed | *bool* | The file or directory is not to be indexed by the content indexing service. |
| o  <br />offline | *bool* | The data of a file is not available immediately. This attribute indicates that the file data is physically moved to offline storage. This attribute is used by Remote Storage, which is the hierarchical storage management software. Applications should not arbitrarily change this attribute. |
| p  <br />pinned | *bool* | The data of the file is to be kept available at all times; it should not be offloaded to offline storage. |
| r  <br />readonly | *bool* | A file that is read-only. Applications can read the file, but cannot write to it or delete it. This attribute is not honored on directories. |
| s  <br />system | *bool* | A file or directory that the operating system uses a part of, or uses exclusively. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Assign | *object:***FileAttr\\** or *string* | none | Assigns a new set of attributes to this object. You can pass another **FileAttr** object, or a string (e.g. *"hsr"*). |
| AttrName | *string* | *string* | Given a single character representing an attribute (e.g. *"a"*) this method returns the name of the attribute in the user's current language (e.g. *"Archive"*). |
| Clear | *object:***FileAttr\\** or *string* | none | Clears (turns off) the specified attributes in this object. You can pass another **FileAttr** object, or a string representing the attributes to turn off. |
| Set | *object:***FileAttr\\** or *string* | none | Sets (turns on) the specified attributes in this object. You can pass another **FileAttr** object, or a string representing the attributes to turn on. |
| ToString | none | none | Returns a string representing the attributes that are set (similar to the format displayed in the *Attr* column in the file display). |

  
