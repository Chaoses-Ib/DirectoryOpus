# FileAttr

**FileAttr** 对象用于简化文件属性的处理。与其将属性视为字符字符串或数字，它提供了可独立设置或查询的每个属性的属性。可以使用 **[FSUtil](fsutil.zh.md).NewFileAttr** 方法创建新的 **FileAttr** 对象。**FileAttr** 对象也作为 **[Format](format.zh.md)** 和 **[Item](item.zh.md)** 对象属性返回。

每个属性由两个属性表示：单个字符（例如 **a**）及其完整名称（例如 **archive**）。如果设置了属性，则每个属性返回 **True**，否则返回 **False**。对于您自己创建的 **FileAttr** 对象，您还可以设置这些属性的值（然后，例如，使用 **[File](file.zh.md).SetAttr** 方法将属性应用于文件）。

  

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>

返回表示已设置属性的字符串（类似于文件列表中 *Attr* 列中显示的格式）。
</td></tr><tr><td>

a  
archive</td><td>

*bool*</td><td>
一个文件或目录，其中包含需要压缩包的更改。A 位通常在新文件或修改的文件上设置，然后在备份软件将更改添加到备份后，可能会被清除。
</td></tr><tr><td>

c  
compressed</td><td>

*bool*</td><td>
一个已压缩的文件或目录。对于文件，文件中的所有数据都已压缩。对于目录，压缩是新创建的文件和子目录的默认值。
</td></tr><tr><td>

e  
encrypted</td><td>

*bool*</td><td>
一个已加密的文件或目录。对于文件，文件中的所有数据流都已加密。对于目录，加密是新创建的文件和子目录的默认值。
</td></tr><tr><td>

h  
hidden</td><td>

*bool*</td><td>
该文件或目录是隐藏的。它不会包含在普通的目录列表中。
</td></tr><tr><td>

i  
nonindexed</td><td>

*bool*</td><td>
该文件或目录不会被内容索引服务索引。
</td></tr><tr><td>

o  
offline</td><td>

*bool*</td><td>
文件的​​数据不可立即获得。此属性表示文件数据已物理移动到脱机存储。此属性由远程存储使用，远程存储是分层存储管理软件。应用程序不应该随意更改此属性。
</td></tr><tr><td>

p  
pinned</td><td>

*bool*</td><td>
文件的​​数据将始终保持可用；它不应该被卸载到脱机存储。
</td></tr><tr><td>

r  
readonly</td><td>

*bool*</td><td>
一个只读文件。应用程序可以读取文件，但不能写入或删除它。此属性不适用于目录。
</td></tr><tr><td>

s  
system</td><td>

*bool*</td><td>
操作系统使用或专门使用的文件或目录。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Assign</td><td>

*object:***FileAttr\\** 或 *string*</td><td>
none</td><td>

将新属性集分配给此对象。您可以传递另一个 **FileAttr** 对象或字符串（例如 *"hsr"*）。
</td></tr><tr><td>
AttrName</td><td>

*string*</td><td>

*string*</td><td>

给定表示属性的单个字符（例如 *"a"*），此方法返回属性在用户当前语言中的名称（例如 *"Archive"*）。
</td></tr><tr><td>
Clear</td><td>

*object:***FileAttr\\** 或 *string*</td><td>
none</td><td>

清除（关闭）此对象中的指定属性。您可以传递另一个 **FileAttr** 对象或表示要关闭的属性的字符串。
</td></tr><tr><td>
Set</td><td>

*object:***FileAttr\\** 或 *string*</td><td>
none</td><td>

设置（打开）此对象中的指定属性。您可以传递另一个 **FileAttr** 对象或表示要打开的属性的字符串。
</td></tr><tr><td>
ToString</td><td>
none</td><td>
none</td><td>

返回表示已设置属性的字符串（类似于文件列表中 *Attr* 列中显示的格式）。
</td></tr></tbody>
</table>

  