# UnorderedSet

**UnorderedSet** 对象是一个存储一个或多个唯一对象的容器。它类似于 **StringSet**，不同之处在于它可以存储任何类型的变体（而不仅仅是字符串），并且内容不保持排序（实际上，集合成员的顺序是未指定的）。与 **StringSet** 一样，它使用字典系统来定位成员，而不是使用数字索引。因此，您可以比线性搜索 **[Vector](vector.zh.md)** 更快地查找成员。

您可以使用 **[DOpusFactory](dopusfactory.zh.md)** 对象创建新的 **UnorderedSet**。

在向 **UnorderedSet** 添加对象时应谨慎。与字符串和数字不同，容器仅在两个对象都是完全相同的对象（即相同的实例/引用）时才认为它们相等。两个具有相同值的独立对象不会被视为相等，并且可以同时存在于同一个 **UnorderedSet** 中。

### JScript 示例：

    var us = DOpus.Create.UnorderedSet();

    us.insert("cat");
    us.insert("cat"); // 无效，因为“cat”已插入。
    us.insert("dog");
    us.insert(DOpus.FSUtil.NewPath("C:\\"));
    us.insert(DOpus.FSUtil.NewPath("C:\\")); // 插入第二个 C:\ Path 对象！

    var p = DOpus.FSUtil.NewPath("D:\\");
    us.insert(p);
    us.insert(p); // 无效，因为 p 已插入。

    DOpus.Output("count: " + us.count);

    for (var e = new Enumerator(us); !e.atEnd(); e.moveNext())
    {
    DOpus.Output("Item: " + e.item());
    }

这将输出以下内容（项目的顺序可能会有所不同）：

    count: 5
    Item: cat
    Item: dog
    Item: D:\
    Item: C:\
    Item: C:\

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>

返回 **UnorderedSet** 当前持有的元素数量。
</td></tr><tr><td>
empty</td><td>

*bool*</td><td>

如果 **UnorderedSet** 为空，则返回 **True**，否则返回 **False**。
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
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
assign</td><td>

\<**UnorderedSet**:from\></td><td>

*none*</td><td>

将另一个 **UnorderedSet** 的内容复制到此 **UnorderedSet**。您还可以传递数组或 **[Vector](vector.zh.md)** 对象。
</td></tr><tr><td>
clear</td><td>

*none*</td><td>

*none*</td><td>

清除 **UnorderedSet** 的内容。
</td></tr><tr><td>
erase</td><td>

*variant*</td><td>

*none*</td><td>
如果元素存在于集合中，则擦除该元素。
</td></tr><tr><td>
exists</td><td>

*variant*</td><td>

*bool*</td><td>

如果指定的元素存在于集合中，则返回 **True**。
</td></tr><tr><td>
insert</td><td>

*variant*</td><td>

*bool*</td><td>

如果元素不存在，则将元素插入集合中。如果成功，则返回 **True**。
</td></tr><tr><td>
merge</td><td>

\<**UnorderedSet**:from\></td><td>

*none*</td><td>

将另一个 **UnorderedSet** 的内容与此 **UnorderedSet** 合并。
</td></tr></tbody>
</table>