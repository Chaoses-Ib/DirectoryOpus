**FileAttr** 对象旨在更容易地处理文件属性。它提供了可独立设置或查询的各个属性，而无需将属性作为字符串或数字进行处理。你可以使用 **[FSUtil](fsutil.zh.md).NewFileAttr** 方法创建一个新的 **FileAttr** 对象。**[Format](format.zh.md)** 和 **[Item](item.zh.md)** 对象的属性也返回  **FileAttr** 对象。

每个属性由两个属性表示：一个单字符（例如 **a**）和它的完整名称（例如 **archive**）。如果设置了属性，则每个属性返回 **True**，否则返回 **False**。对于自己创建的 **FileAttr** 对象，还可以设置这些属性的值（然后，例如，可以使用 **[File](file.zh.md).SetAttr** 方法将属性应用到文件）。

  

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*string*</td><td>

返回一个字符串，表示已设置的属性（类似于文件列表中 *Attr* 列中显示的格式）。
</td></tr><tr><td>

a  
压缩包</td><td>

*bool*</td><td>
需要压缩包的文件或目录。A 位通常在新的或修改过的文件上设置，然后可以在备份软件将更改添加到备份后将其清除。
</td></tr><tr><td>

c  
压缩</td><td>

*bool*</td><td>
压缩的文件或目录。对于文件，文件中的所有数据都被压缩。对于目录，压缩是新创建文件和子目录的默认设置。
</td></tr><tr><td>

e  
加密</td><td>

*bool*</td><td>
加密的文件或目录。对于文件，文件中的所有数据流都经过加密。对于目录，加密是新创建文件和子目录的默认设置。
</td></tr><tr><td>

h  
隐藏</td><td>

*bool*</td><td>
隐藏文件或目录。它不包含在普通目录列表中。
</td></tr><tr><td>

i  
未编入索引</td><td>

*bool*</td><td>
文件或目录不会被内容索引服务编入索引。
</td></tr><tr><td>

o  
脱机</td><td>

*bool*</td><td>
文件的数据不可立即使用。此属性表示文件数据已物理移动到脱机存储中。此属性由远程存储（一种分层存储管理软件）使用。应用程序不应该随意更改此属性。
</td></tr><tr><td>

p  
已固定</td><td>

*bool*</td><td>
文件的应始终保持数据可用；它不应该被卸载到脱机存储。
</td></tr><tr><td>

r  
只读</td><td>

*bool*</td><td>
只读文件。应用程序可以读取文件，但不能写入或删除文件。目录中不包含此属性。
</td></tr><tr><td>

s  
系统</td><td>

*bool*</td><td>
文件或目录由操作系统作为其一部分使用，或者完全使用该部分。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
分配</td><td>

*对象：***FileAttr\\** 或 *string*</td><td>
无</td><td>

将一组新的属性分配给此对象。你可以传递另一个 **FileAttr** 对象或字符串（例如 *"hsr"*）。
</td></tr><tr><td>
属性名称</td><td>

*string*</td><td>

*string*</td><td>

给定表示属性的单字符（例如 *"a"*），此方法返回用户当前语言中属性的名称（例如 *"Archive"*）。
</td></tr><tr><td>
清除</td><td>

*对象：***FileAttr\\** 或 *string*</td><td>
无</td><td>

清除（关闭）此对象中指定的属性。你可以传递另一个 **FileAttr** 对象或一个字符串，表示要关闭的属性。
</td></tr><tr><td>
设置</td><td>

*对象：***FileAttr\\** 或 *string*</td><td>
无</td><td>

设置（打开）此对象中指定的属性。你可以传递另一个 **FileAttr** 对象或一个字符串，表示要打开的属性。
</td></tr><tr><td>
ToString</td><td>
无</td><td>
无</td><td>

返回一个字符串，表示已设置的属性（类似于文件列表中 *Attr* 列中显示的格式）。
</td></tr></tbody>
</table>

  
