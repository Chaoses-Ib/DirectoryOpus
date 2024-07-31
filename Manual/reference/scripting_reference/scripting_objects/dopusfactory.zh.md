# DOpusFactory

**DOpusFactory** 对象是一个辅助对象，您可以使用它来创建各种其它对象。与表示现有*事物*的对象（例如 **[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**）不同，由 **DOpusFactory** 创建的对象是独立对象，您可以在需要其功能时随时实例化它们。**DOpusFactory** 对象可以通过 **[DOpus](dopus.zh.md).Create** 方法获得。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Blob</td><td>

*无*  
或 \<int:size\>  
或 <nobr>\<byte, byte, ...\></nobr>  
或 \<**[Blob](blob.zh.md)**:source\></td><td>

*对象:***[Blob](blob.zh.md)**</td><td>

返回一个新的 **[Blob](blob.zh.md)** 对象，它允许您从脚本访问和操作一段二进制数据。如果没有给出参数，新的 **Blob** 将为空 - 您可以使用 **resize** 方法设置其大小 - 否则您可以指定初始大小作为参数。

您还可以通过指定实际字节值（例如 *Blob(72,69,76,76,79)*）来创建一个预先填充数据的 **Blob**。

如果给出了另一个 **Blob**（或数组 - 有关此的讨论，请参阅 **Blob** 对象的文档），则将创建新的 **Blob** 作为现有 **Blob** 的副本。
</td></tr><tr><td>
BusyIndicator</td><td>

*无*</td><td>

*对象:***[BusyIndicator](busyindicator.zh.md)**</td><td>

创建一个新的 **[BusyIndicator](busyindicator.zh.md)** 对象，它允许您从脚本控制面包屑栏繁忙指示器。
</td></tr><tr><td>
Command</td><td>

*无*</td><td>

*对象:***[Command](command.zh.md)**</td><td>

创建一个新的 **[Command](command.zh.md)** 对象，它允许您从脚本运行 Opus 命令。
</td></tr><tr><td>
Date</td><td>

*无*  
或 \<variant:date\>  
或 *JScript Date*</td><td>

*对象*:**[Date](date.zh.md)**</td><td>

创建一个新的 **[Date](date.zh.md)** 对象。如果提供日期值，则新对象将初始化为该值，否则日期将设置为当前本地时间。提供的 value 可以是以下之一：

- 另一个 **Date** 对象
- 格式为 "yyyymmdd" 的字符串
- 格式为 "yyyy-mm-dd hh:mm:ss.mmm"（或部分）的字符串
- JScript **Date** 对象
- Unix 时间戳值（自 1970 年 1 月 1 日以来的秒数）。
</td></tr><tr><td>
Filter</td><td>

*无*  
或 \<string\></td><td>

*对象:***[Filter](filter.zh.md)**</td><td>

创建一个新的 **[Filter](filter.zh.md)** 对象，它允许您在从脚本运行命令时控制递归过滤。您可以选择提供一个 [文本过滤器](/Manual/file_operations/filtered_operations/textual_filters.zh.md) 字符串来初始化过滤器。检查新 **Filter** 对象的 **valid** 属性以确定此字符串是否成功解析。
</td></tr><tr><td>
Map</td><td>

*无*  
或 \<variant:key\>,  
\<variant:value\>...</td><td>

*对象*:**[Map](map.zh.md)**</td><td>

创建一个新的 **[Map](map.zh.md)** 对象。如果没有提供参数，**Map** 将为空。否则，**Map** 将使用提供的键/值对进行预初始化。

//For <example://>

    Map("firstname","fred","lastname","bloggs");

各个键和值可以是不同的类型。
</td></tr><tr><td>
OrderedMap</td><td>

*无*  
或 \<variant:key\>,  
\<variant:value\>...</td><td>

*对象*:**[OrderedMap](orderedmap.zh.md)**</td><td>

创建一个新的 **[OrderedMap](orderedmap.zh.md)** 对象。这与 [Map](Map.zh.md) 对象相同，只是它保留添加到映射中的项目的顺序，而不是按字母顺序排序。
</td></tr><tr><td>
StringSet</td><td>

*无*  
或 \<string\>, ...</td><td>

*对象*:**[StringSet](stringset.zh.md)**</td><td>

创建一个新的区分大小写的 **[StringSet](stringset.zh.md)** 对象。如果没有提供参数，**StringSet** 将为空。否则它将使用提供的字符串进行预初始化；例如：

    StringSet("dog","cat","pony");

您还可以传递字符串数组或 **[Vector](vector.zh.md)** 对象来初始化集合。
</td></tr><tr><td>
StringSetI</td><td>

*无*  
或 \<string\>, ...</td><td>

*对象*:**[StringSet](stringset.zh.md)**</td><td>

创建一个新的不区分大小写的 **[StringSet](stringset.zh.md)** 对象。如果没有提供参数，**StringSet** 将为空。否则它将使用提供的字符串进行预初始化。
</td></tr><tr><td>
StringTools</td><td>

*无*</td><td>

*对象*:**[StringTools](stringtools.zh.md)**</td><td>

创建一个新的 **[StringTools](stringtools.zh.md)** 对象，它提供字符串编码和解码的辅助函数。
</td></tr><tr><td>
UnorderedSet</td><td>

*无*  
或 *variants*...</td><td>

object:**[UnorderedSet](unorderedset.zh.md)**</td><td>

创建一个新的 **[UnorderedSet](unorderedset.zh.md)** 对象。如果没有提供参数，**UnorderedSet** 将为空。否则它将使用提供的元素进行预初始化。

您还可以传递数组或 **[Vector](vector.zh.md)** 来初始化集合。
</td></tr><tr><td>
Vector</td><td>

*无*  
或 \<int:elements\>  
或 *variants...*  
或 *object:***[vector](vector.zh.md)**  
或 *JScript Array*</td><td>

*对象:***[Vector](vector.zh.md)**</td><td>

创建一个新的 **[Vector](vector.zh.md)** 对象。

如果没有提供参数，**Vector** 将为空。

如果提供单个整数参数，**Vector** 将预初始化为该元素数量。

您还可以传递另一个 **[Vector](vector.zh.md)** 或 *JScript* 数组，或大多数可枚举对象，作为参数来使用现有集合的内容初始化新的 **Vector**。

如果提供多个参数，**Vector** 将使用这些元素进行预初始化；例如：

    Vector("dog","cat","horse");

各个元素可以是不同的类型。

如果您想创建一个只有一个元素的 **Vector**，最好创建一个空的 **Vector**，然后在第二步添加该元素。在创建期间传递单个元素可能会产生意外结果，因为它可能被解释为其它情况之一。（许多脚本对象可以隐式转换为整数或集合。）
</td></tr></tbody>
</table>