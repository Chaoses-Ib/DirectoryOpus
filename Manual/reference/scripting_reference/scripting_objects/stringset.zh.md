**StringSet** 对象是一个容器，用于存储一个或多个唯一的字符串。它类似于数组或向量（例如，**[Vector](vector.zh.md)**），但其优势在于使用字典系统来定位字符串，而不是使用数字索引。因此，您可以比线性搜索 **[Vector](vector.zh.md)** 更快速地查找字符串。

您可以使用 **[DOpusFactory](dopusfactory.zh.md)** 对象创建新的 **StringSet**。**StringSet** 可以区分大小写（“cat” 和 “CAT” 将被视为两个不同的字符串），也可以不区分大小写。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
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
说明
</th></tr></thead><tbody><tr><td>
assign</td><td>

\<**StringSet**:from\></td><td>

*none*</td><td>

将另一个 **StringSet** 的内容复制到这个 **StringSet** 中。您还可以传递字符串数组或 **[Vector](vector.zh.md)** 对象。
</td></tr><tr><td>
clear</td><td>

*none*</td><td>

*none*</td><td>

清除 **StringSet** 的内容。
</td></tr><tr><td>
erase</td><td>

\<string\></td><td>

*none*</td><td>
如果字符串存在于集合中，则将其擦除。
</td></tr><tr><td>
exists</td><td>

\<string\></td><td>

*bool*</td><td>

如果指定字符串存在于集合中，则返回 **True**。
</td></tr><tr><td>
insert</td><td>

\<string\></td><td>

*bool*</td><td>

如果字符串不存在，则将其插入到集合中。如果成功，则返回 **True**。
</td></tr><tr><td>
merge</td><td>

\<**StringSet**:from\></td><td>

*none*</td><td>

将另一个 **StringSet** 的内容与这个 **StringSet** 合并。
</td></tr></tbody>
</table>