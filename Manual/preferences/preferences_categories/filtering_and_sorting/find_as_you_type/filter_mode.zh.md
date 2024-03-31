# 过滤模式

此页面提供有关 [即时查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 字段的“过滤”模式的选项。过滤模式允许您根据文件名过滤当前显示的文件夹。

- **允许 <kbd>Enter</kbd> 键打开所选项目**：按 <kbd>Enter</kbd> 键将打开具有焦点的项目，而不仅仅是关闭即时查找。
- **选择第一个匹配的项目**：将自动选择与过滤器匹配的第一个项目。

### 过滤模式

（Opus 13.3.4 及以上版本）这些选项控制过滤器的行为。

- **忽略变音符号**：过滤时将忽略变音符号或重音符号。因此，例如，普通的“e”将与“é”相同。

- **匹配任意单词**：此选项将您输入的所有单词视为独立的模式。例如，可以输入“moo cow”，它将自动匹配名为“moo”或名为“cow”的文件。这样便不必构建复杂的*OR*通配符（等效通配符为`(moo|cow)`）。还可以使用`+`和`-`分别明确包含或排除单词 - 有关更多详细信息，请参见 [过滤栏](/Manual/basic_concepts/searching_and_filtering/filter_bar.zh.md) 页面。

- **部分匹配**：开启后，过滤将自动在子字符串中进行匹配，所以输入“og”将匹配包含这些字母的任何文件，例如“dog.txt”或“google.png”。关闭后，输入的模式必须完全匹配 - 因此需要输入“*og*”才能获得相同的效果。请注意，如果明确在模式的开头或结尾添加“*”，则 Opus 将认为即使开启了部分匹配也不希望使用它。这使您在大多数情况下能够方便地进行部分匹配，同时还能够在需要时按事物的开头或结尾过滤。

- **使用正则表达式**：启用后，输入到中的模式将被视为 [正则表达式](/Manual/reference/wildcard_reference/regular_expression_syntax.zh.md)，而不是简单通配符。

- **求值器**：（Opus 13.3.4 及以上版本）在求值器模式下，快速过滤表达式会传递给列表中每个项目的 [求值器](/Manual/evaluator/README.zh.md)。如果应显示项目，则表达式应返回 **true**；如果应隐藏项目，则表达式应返回 **false**。可以使用求值器代码，还可以使用 `?filtername` 调用预定义的 [过滤器](/Manual/file_operations/filtered_operations/README.zh.md)。如果预定义的过滤器也使用求值器代码，则可以通过名称向其传递参数。例如，`?bigfiles:5` 将调用名为“bigfiles”的预定义过滤器，并将值“5”作为变量传递给它。有关更多信息，请参阅 [求值器过滤器和查找](/Manual/evaluator/applicable_contexts/filters_and_find.zh.md)。