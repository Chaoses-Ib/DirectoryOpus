# StringSet

**StringSet** 对象是一个存储一个或多个唯一字符串的容器。它类似于数组或向量（例如 **[Vector](vector.zh.md)**），但它使用字典系统来定位字符串，而不是数字索引。因此，你可以比线性搜索 **[Vector](vector.zh.md)** 更快地查找字符串。

你可以使用 **[DOpusFactory](dopusfactory.zh.md)** 对象创建一个新的 **StringSet**。**StringSet** 可以是区分大小写的（"cat" 和 "CAT" 将被视为两个不同的字符串），也可以是不区分大小写的。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>

返回 **StringSet** 当前持有的元素数量。
</td></tr><tr><td>
empty</td><td>

*bool*</td><td>

如果 **StringSet** 为空，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
length</td><td>

*int*</td><td>

**count** 的同义词。
</td></tr><tr><td>
size</td><td>

*int*</td><td>

**count** 的同义词。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
assign</td><td>

\<**StringSet**:from\></td><td>

*none*</td><td>

将另一个 **StringSet** 的内容复制到当前 **StringSet** 中。你也可以传递一个字符串数组或 **[Vector](vector.zh.md)** 对象。
</td></tr><tr><td>
clear</td><td>

*none*</td><td>

*none*</td><td>

清除 **StringSet** 的内容。
</td></tr><tr><td>
erase</td><td>

\<string\></td><td>

*none*</td><td>
如果字符串存在于集合中，则擦除它。
</td></tr><tr><td>
exists</td><td>

\<string\></td><td>

*bool*</td><td>

如果指定的字符串存在于集合中，则返回 **True**。
</td></tr><tr><td>
insert</td><td>

\<string\></td><td>

*bool*</td><td>

如果字符串不存在于集合中，则将其插入集合中。如果成功，则返回 **True**。
</td></tr><tr><td>
merge</td><td>

\<**StringSet**:from\></td><td>

*none*</td><td>

将另一个 **StringSet** 的内容与当前 **StringSet** 合并。
</td></tr></tbody>
</table>