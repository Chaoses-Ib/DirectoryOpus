**DOpusFactory** 对象是一个帮助对象，可以通过它创建各种其他对象。与表示已有 *事物*（例如 **[文件窗口](lister.zh.md)** 或 **[Tab](tab.zh.md)**）的对象不同，**DOpusFactory** 创建的对象是独立对象，可以在需要其功能时对其进行实例化。**DOpusFactory** 对象是通过 **[DOpus](dopus.zh.md).Create** 方法获得的。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Blob</td><td>

*无*  
或 \<int:size\>  
或 <nobr>\<byte, byte, ...\></nobr>  
或 \<**[Blob](blob.zh.md)**:source\></td><td>

*object:***[Blob](blob.zh.md)**</td><td>

返回一个新的 **[Blob](blob.zh.md)** 对象，通过它可以从脚本访问和处理二进制数据块。如果没有给出参数，则新 **Blob** 将为空 - 可以使用 **resize** 方法设置其大小 - 否则，可以将初始大小指定为参数。

还可以通过指定实际字节值（例如 *Blob(72,69,76,76,79)*）来创建预先填充好数据的 **Blob**。

如果给出了另一个 **Blob**（或数组 - 有关此内容的讨论，请参阅 **Blob** 对象的说明），则新 **Blob** 将创建为现有 **Blob** 的副本。
</td></tr><tr><td>
BusyIndicator</td><td>

*无*</td><td>

*object:***[BusyIndicator](busyindicator.zh.md)**</td><td>

创建一个新的 **[BusyIndicator](busyindicator.zh.md)** 对象，通过它可以从脚本控制面包屑栏忙状态指示器。
</td></tr><tr><td>
Command</td><td>

*无*</td><td>

*object:***[Command](command.zh.md)**</td><td>

创建一个新的 **[Command](command.zh.md)** 对象，通过它可以从脚本运行 Opus 命令。
</td></tr><tr><td>
Date</td><td>

*无*  
或 \<variant:date\>  
或 *JScript Date*</td><td>

*object*:**[Date](date.zh.md)**</td><td>

创建一个新的 **[Date](date.zh.md)** 对象。如果提供了日期值，则新对象将初始化为该值，否则该日期将设置为当前本地时间。提供的数值可以为以下之一：

- 另一个 **Date** 对象
- "yyyymmdd" 形式的字符串
- "yyyy-mm-dd hh:mm:ss.mmm" 形式的字符串（或其的一部分）
- JScript **Date** 对象
- unix 纪元时间值（自 1/1/1970 以来的秒数）。
</td></tr><tr><td>
Filter</td><td>

*无*  
或 \<string\></td><td>

*object:***[Filter](filter.zh.md)**</td><td>

创建一个新的 **[Filter](filter.zh.md)**对象，通过它在从脚本运行命令时控制递归过滤。可以选择提供 [文本过滤](/Manual/file_operations/filtered_operations/textual_filters.zh.md) 字符串，以此初始化过滤。检查新 **Filter** 对象的 **valid** 属性，以了解是否成功解析了此字符串。
</td></tr><tr><td>
Map</td><td>

*无*  
或 \<variant:key\>,  
\<variant:value\>...</td><td>

*object*:**[Map](map.zh.md)**</td><td>

创建一个新的 **[Map](map.zh.md)** 对象。如果没有提供参数，**Map** 将为空。否则，将使用提供的键/值对预先初始化 **Map**。

//如 <example://>

    Map("firstname","fred","lastname","bloggs");

各个键和值可以是不同类型。
</td></tr><tr><td>
StringSet</td><td>

*无*  
或 \<string\>, ...</td><td>

*object*:**[StringSet](stringset.zh.md)**</td><td>

创建新的区分大小写的 **[StringSet](stringset.zh.md)** 对象。如果没有提供参数，**StringSet** 将为空。否则，它将使用提供的字符串进行预先初始化；例如：

    StringSet("dog","cat","pony");

还可以传递字符串数组或 **[Vector](vector.zh.md)** 对象来初始化集合。
</td></tr><tr><td>
StringSetI</td><td>

*无*  
或 \<string\>, ...</td><td>

*object*:**[StringSet](stringset.zh.md)**</td><td>

创建新的不区分大小写的 **[StringSet](stringset.zh.md)** 对象。如果没有提供参数，**StringSet** 将为空。否则，它将使用提供的字符串进行预先初始化。
</td></tr><tr><td>
StringTools</td><td>

*无*</td><td>

*object*:**[StringTools](stringtools.zh.md)**</td><td>

创建一个新的 **[StringTools](stringtools.zh.md)** 对象，该对象提供用于字符串编码和解码的帮助器函数。
</td></tr><tr><td>
UnorderedSet</td><td>

*无*  
或 *variants*...</td><td>

object:**[UnorderedSet](unorderedset.zh.md)**</td><td>

创建一个新的 **[UnorderedSet](unorderedset.zh.md)** 对象。如果没有提供参数，**UnorderedSet** 将为空。否则，将使用提供的元素进行预先初始化。

还可以传递数组或 **[Vector](vector.zh.md)** 来初始化集合。
</td></tr><tr><td>
Vector</td><td>

*无*  
或 \<int:elements\>  
或 *variants...*  
或 *object:***[vector](vector.zh.md)**  
或 *JScript 数组*</td><td>

*object:***[Vector](vector.zh.md)**</td><td>

创建一个新的 **[Vector](vector.zh.md)** 对象。

如果没有提供参数，**Vector** 将为空。

如果提供了单个整型参数，则 **Vector** 将预先初始化为该数值的元素。

还可以传递另一个 **[Vector](vector.zh.md)** 或 *JScript* 数组，也可以传递大多数可枚举对象，作为参数，以便使用现有集合的内容初始化新 **Vector**。

如果提供了多个参数，则 **Vector** 将使用这些元素进行预先初始化；例如：

    Vector("dog","cat","horse");

各个元素可以是不同类型。

如果想要创建只有一个元素的 **Vector**，最好创建一个空 **Vector**，然后在第二步中添加元素。在创建过程中传递单个元素可能会产生意外结果，因为它可能会被解释为其他案例之一。（许多脚本对象都可以隐式转换为整数或集合。）
</td></tr></tbody>
</table>