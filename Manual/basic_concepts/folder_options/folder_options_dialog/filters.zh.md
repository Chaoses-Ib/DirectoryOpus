# 过滤器

文件夹格式对话中的**隐藏过滤器**和**显示过滤器**标签看似相同。它们均可用于控制格式应用于文件夹时哪些文件和文件夹应显示，哪些应隐藏。

- **显示过滤器**标签中的设置导致与过滤器**不**匹配的项会被隐藏。
- **隐藏过滤器**标签中的设置导致与过滤器**匹配**的项会被隐藏。

**文件名**和**文件夹名**字段采用使用[标准模式匹配](/Manual/reference/wildcard_reference/pattern_matching_syntax.zh.md)或[正则表达式语法](/Manual/reference/wildcard_reference/regular_expression_syntax.zh.md)（如果开启了**使用正则表达式**选项）表达的通配符字符串。

**属性**字段使您可以基于属性过滤文件和文件夹 - 如果该项上设置了任何所选属性，则该项将匹配过滤器，并根据需要显示或隐藏。

显示和隐藏过滤器都具有针对文件夹的单独属性过滤器的选项。如果启用了这些单独过滤器，则每个组中第一个 **属性** 字段仅适用于文件 - 否则，它适用于文件和文件夹。

这些过滤器置于[全局过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/global_filters.zh.md)之上。

可以通过切换[显示全部](../../searching_and_filtering/show_everything.zh.md)模式在文件夹标签中快速禁用所有过滤。