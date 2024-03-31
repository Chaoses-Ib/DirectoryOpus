**UnorderedSet** 对象是一个容器，用于存储一个或多个唯一对象。它类似于 StringSet，除了它可以存储任何类型的变量（而不仅仅是字符串），并且内容不会按顺序保存（事实上，没有指定集合成员的顺序）。和 StringSet 一样，它使用字典系统查找成员，而不是数字索引。因此，你可以比通过线性搜索**[矢量](vector.zh.md)** 更快地查找成员。

你可以使用 **[DOpusFactory](dopusfactory.zh.md)** 对象创建一个新的 **UnorderedSet**。

向 **UnorderedSet** 添加对象时应小心。与字符串和数字不同，容器只会将两个对象视为相等，如果它们是同一个对象（即相同的实例/引用）。具有相同值的不同对象不会被视为相等，并且可以同时存在于同一个 **UnorderedSet** 中。

##### JScript 示例：

> **var** us = DOpus.Create.UnorderedSet();

> us.insert("cat");
> us.insert("cat"); // 无效，因为已插入 "cat"。
> us.insert("dog");
> us.insert(DOpus.FSUtil.NewPath("C:\\"));
> us.insert(DOpus.FSUtil.NewPath("C:\\")); // 插入另一个 C:\ 路径对象！

> **var** p = DOpus.FSUtil.NewPath("D:\\");
> us.insert(p);
> us.insert(p); // 无效，因为已插入 p。

> DOpus.Output("count: " + us.count);

> **for** (**var** e = **new** Enumerator(us); !e.atEnd(); e.moveNext())
> {
> DOpus.Output("Item: " + e.item());
> }

它将输出以下内容（项目顺序可能有所不同）：

> count: 5
> Item: cat
> Item: dog
> Item: D:\
> Item: C:\
> Item: C:\

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>

返回 **UnorderedSet** 当前包含的元素数量。
</td></tr><tr><td>
empty</td><td>

*bool*</td><td>

如果 **UnorderedSet** 为空，则返回 **True**；如果不为空，则返回 **False**。
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

\<**UnorderedSet**:from\></td><td>

*none*</td><td>

将另一个 **UnorderedSet** 的内容复制到此 **UnorderedSet**。你还可以传递数组或 **[Vector](vector.zh.md)** 对象。
</td></tr><tr><td>
clear</td><td>

*none*</td><td>

*none*</td><td>

清除 **UnorderedSet** 的内容。
</td></tr><tr><td>
erase</td><td>

*variant*</td><td>

*none*</td><td>
如果元素存在于集合中，则将其删除。
</td></tr><tr><td>
exists</td><td>

*variant\\*</td><td>

*bool*</td><td>

如果指定元素存在于集合中，则返回 **True**。
</td></tr><tr><td>
insert</td><td>

*variant*</td><td>

*bool*</td><td>

如果元素不存在，则将其插入集合中。如果成功，则返回 **True**。
</td></tr><tr><td>
merge</td><td>

\<**UnorderedSet**:from\></td><td>

*none*</td><td>

将另一个 **UnorderedSet** 的内容与当前 **UnorderedSet** 合并。
</td></tr></tbody>
</table>