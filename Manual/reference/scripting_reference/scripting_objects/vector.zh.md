# Vector

**Vector** 对象旨在解决 ActiveX 脚本中数组支持的一些不足之处。一些语言对数组的支持比其它语言更好，但这些语言并不一致，有些语言（如 *JScript*）具有 Opus 无法访问的互不兼容的数组。因此，任何接受或返回类似数组变量的 Opus 脚本对象都将使用（或优先使用）**Vector** 而不是数组。

**Vector** 对象大部分可以作为数组的直接替代品。它们是 *集合*，因此可以枚举，或者通过索引访问（例如 **Vector(4)** 访问第五个元素）。它们还有一些辅助方法，使操作它们比操作数组更容易。

请注意，在 *JScript* 中，您可以使用方括号（就像数组一样）或圆括号（就像它是函数参数一样）访问元素。在其它语言（如 *VBScript*）中，您只能使用圆括号。

您可以使用 **[DOpusFactory](dopusfactory.zh.md).Vector** 方法创建新的 **Vector**。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
capacity</td><td>

*int*</td><td>

返回 **Vector** 的容量（它可以在不重新分配内存的情况下容纳的元素数量）。这与它当前容纳的元素数量不同，即使容量较大，它当前容纳的元素数量也可能为 0。
</td></tr><tr><td>
count</td><td>

*int*</td><td>

返回 **Vector** 当前容纳的元素数量。
</td></tr><tr><td>
empty</td><td>

*bool*</td><td>

如果 **Vector** 为空，则返回 **True**，否则返回 **False**。
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
append</td><td>

\<**Vector**:from\>  
\<int:start\>  
\<int:end\></td><td>

*none*</td><td>

将另一个 **Vector** 的值复制到此 **Vector** 的末尾，同时保留现有的值。如果没有提供 *start* 和 *end*，则将附加整个 **Vector** - 否则，只附加指定的元素。

除了 **Vector** 对象之外，您还可以将 *集合* 传递给此方法，并将集合的内容复制到 **Vector** 的末尾。  
在 *JScript* 中，您可以将标准数组传递给此方法以将数组复制到 **Vector** 的末尾。
</td></tr><tr><td>
assign</td><td>

\<**Vector**:from\>  
\<int:start\>  
\<int:end\></td><td>

*none*</td><td>

将另一个 **Vector** 的值复制到此 **Vector**。如果没有提供 *start* 和 *end*，则将复制整个 **Vector** - 否则，只复制指定的元素。

除了 **Vector** 对象之外，您还可以将 *集合* 传递给此方法，并将集合的内容复制到 **Vector**。

在 *JScript* 中，您可以将标准数组传递给此方法以将数组复制到 **Vector**。
</td></tr><tr><td>
back</td><td>

*none*</td><td>

*variant*</td><td>

返回 **Vector** 中的最后一个元素。
</td></tr><tr><td>
clear</td><td>

*none*</td><td>

*none*</td><td>

清除 **Vector** 的内容。
</td></tr><tr><td>
erase</td><td>

\<int:index\></td><td>

*none*</td><td>
删除指定索引处的元素。
</td></tr><tr><td>
exchange</td><td>

\<int:index1\>  
\<int:index2\></td><td>

*none*</td><td>
交换两个指定元素的位置。
</td></tr><tr><td>
front</td><td>

*none*</td><td>

*variant*</td><td>

返回 **Vector** 中的第一个元素。
</td></tr><tr><td>
insert</td><td>

\<int:index\>  
\<variant:value\></td><td>

*none*</td><td>
在指定位置插入提供的 value。
</td></tr><tr><td>
pop_back</td><td>

*none*</td><td>

*none*</td><td>

删除 **Vector** 的最后一个元素。
</td></tr><tr><td>
push_back</td><td>

\<variant:value\></td><td>

*none*</td><td>

将提供的 value 添加到 **Vector** 的末尾。
</td></tr><tr><td>
reserve</td><td>

\<int:capacity\></td><td>

*none*</td><td>

在 **Vector** 中为指定数量的元素预留空间（增加其 **capacity**，尽管元素的 **count** 保持不变）。

请注意，**Vector** 会动态增长 - 您不必专门预留或调整它们的大小。但是，如果您想向 **Vector** 添加大量元素，则预先为它们预留空间可能会更有效。
</td></tr><tr><td>
resize</td><td>

\<int:size\></td><td>

*none*</td><td>

将 **Vector** 调整为指定数量的元素。**Vector** 新大小之后的任何现有元素都将被删除。
</td></tr><tr><td>
reverse</td><td>

*none*</td><td>

*none*</td><td>

反转 **Vector** 持有的元素的顺序。
</td></tr><tr><td>
shrink_to_fit</td><td>

*none*</td><td>

*none*</td><td>

将 **Vector** 的容量缩减到它当前容纳的元素数量。
</td></tr><tr><td>
sort</td><td>

*none*</td><td>

*none*</td><td>

对 **Vector** 的内容进行排序。字符串和数字按字母顺序和数字顺序排序 - 其它元素按类型分组，但没有按任何特定顺序排序。
</td></tr><tr><td>
unique</td><td>

*none*</td><td>

*int*</td><td>

从 **Vector** 中删除除一个之外的所有重复元素。返回删除的元素数量。
</td></tr></tbody>
</table>