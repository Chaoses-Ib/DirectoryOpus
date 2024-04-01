# 正则表达式

“正则表达式”模式让你能够使用正则表达式执行批处理重命名，以指定搜索和替换模式。

![](/Manual/images/media/13/regular_expression_rename.png)

上面的示例展示了一个非常简单的正则表达式，它用于删除原始文件名中的下划线。*(.\*)\_(.\*)* 的“旧名称”模式使用括号标记两个“匹配所有内容”表达式，而*New name* 模式中的 *\1\2* 在新名称中插入两个标记表达式的值。

Directory Opus 提供的一项扩展功能是能够使用正则表达式执行重复搜索和替换。上述示例只会删除一个下划线，但如果你想从源名称中删除所有下划线，可以将 \#（磅/散列）符号附加到“旧名称”模式。这将导致 Opus 重复搜索和替换，直到新文件名不再发生变化。

请参见 [正则表达式语法](/Manual/reference/wildcard_reference/regular_expression_syntax.zh.md) 参考页面，了解有关使用正则表达式的更多信息。可以在 [Microsoft 的 TR1 ECMAScript 简介](http://msdn.microsoft.com/en-us/library/bb982727.aspx) 中找到其它信息（Opus 默认使用的正则表达式类型）以获取更多信息，如果你需要帮助，可以向 [Opus Resource Centre](http://resource.dopus.com/) 提问。