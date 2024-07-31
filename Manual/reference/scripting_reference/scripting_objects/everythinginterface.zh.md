# EverythingInterface

如果安装了 [Everything](/Manual/additional_functionality/everything_integration.zh.md) (由 voidtools 开发)，它将提供一个接口，让您能够轻松地从脚本与 Everything 进行通信。您可以启动和停止 Everything，查询其状态，向其发送任意命令以及查询其数据库。

通过 **[DOpus](dopus.zh.md).Create** 工厂方法创建一个 **EverythingInterface** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
autorun</td><td>

*bool*</td><td>

如果 Everything 被配置为自动启动（通过 **[杂项 / 高级选项](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 偏好设置页面），则返回 True。
</td></tr><tr><td>
indexed</td><td>

*int*</td><td>

返回一个值，指示 Everything 被配置为索引哪些属性。这是一个由以下值组成的位掩码：

|     |               |
|-----|---------------|
| 2   | 文件大小    |
| 4   | 文件夹大小  |
| 8   | 创建时间  |
| 16  | 修改时间 |
| 32  | 访问时间 |
| 64  | 属性    |
</td></tr><tr><td>
isrunning</td><td>

*bool*</td><td>
如果 Everything 正在运行，则返回 True。
</td></tr><tr><td>
roots</td><td>

*object:***[StringSet](stringset.zh.md)**</td><td>
返回一个集合，表示 Everything 已索引的驱动器根目录。
</td></tr><tr><td>
version</td><td>

*string*</td><td>
返回 Everything 的版本号。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Indexed</td><td>

\<string:path\></td><td>

*bool*</td><td>
如果指定的路径被 Everything 索引，则返回 True。
</td></tr><tr><td>
Query</td><td>

\<query\>  
\<search_flags\>  
\<request_flags\>  
\<sort_type\>  
\<max_results\>  
\<offset\>  
\<timeout\></td><td>

**[Vector](vector.zh.md)** of **[EverythingResult](everythingresult.zh.md)**</td><td>

将指定的查询字符串发送到 Everything。将结果作为 [Vector](vector.zh.md) of [EverythingResult](everythingresult.zh.md) 对象返回。

查询字符串后面的所有参数都是可选的，它们表示 Everything API 提供的标志。

*search_flags* 应该是一个位掩码，表示 `EVERYTHING_IPC_xxx` 搜索标志，或者是一个包含以下一个或多个字符的字符串。如果没有提供，则默认为 `0`。

|     |                                                                                           |
|-----|-------------------------------------------------------------------------------------------|
| c   | 匹配大小写 (`EVERYTHING_IPC_MATCHCASE`)              |
| w   | 匹配整个单词 (`EVERYTHING_IPC_MATCHWHOLEWORDS`) |
| p   | 匹配路径 (`EVERYTHING_IPC_MATCHPATH`)              |
| r   | 正则表达式 (`EVERYTHING_IPC_REGEX`)                       |
| a   | 匹配重音符号 (`EVERYTHING_IPC_MATCHACCENTS`)        |

*request_flags* 应该是一个位掩码，表示 `EVERYTHING_IPC_QUERY2_REQUEST_xxx` 请求标志，或者是一个包含以下一个或多个字符的字符串。如果没有提供，则默认为 `EVERYTHING_IPC_QUERY2_REQUEST_FULL_PATH_AND_NAME`。

|     |                                                                                                                                      |
|-----|--------------------------------------------------------------------------------------------------------------------------------------|
| n   | 名称 (`EVERYTHING_IPC_QUERY2_REQUEST_NAME`)                                                     |
| p   | 路径 (`EVERYTHING_IPC_QUERY2_REQUEST_PATH`)                                                     |
| f   | 完整路径和名称 (`EVERYTHING_IPC_QUERY2_REQUEST_FULL_PATH_AND_NAME`)                         |
| x   | 扩展名 (`EVERYTHING_IPC_QUERY2_REQUEST_EXTENSION`)                                           |
| s   | 大小 (`EVERYTHING_IPC_QUERY2_REQUEST_SIZE`)                                                     |
| c   | 创建时间 (`EVERYTHING_IPC_QUERY2_REQUEST_DATE_CREATED`)                                          |
| m   | 修改时间 (`EVERYTHING_IPC_QUERY2_REQUEST_DATE_MODIFIED`)                                        |
| e   | 访问时间 (`EVERYTHING_IPC_QUERY2_REQUEST_DATE_ACCESSED`)                                        |
| a   | 属性 (`EVERYTHING_IPC_QUERY2_REQUEST_ATTRIBUTES`)                                         |
| r   | 运行次数 (`EVERYTHING_IPC_QUERY2_REQUEST_RUN_COUNT`)                                           |
| R   | 运行日期 (`EVERYTHING_IPC_QUERY2_REQUEST_DATE_RUN`)                                             |
| M   | 最近更改日期 (`EVERYTHING_IPC_QUERY2_REQUEST_DATE_RECENTLY_CHANGED`)                   |
| N   | 高亮名称 (`EVERYTHING_IPC_QUERY2_REQUEST_HIGHLIGHTED_NAME`)                             |
| P   | 高亮路径 (`EVERYTHING_IPC_QUERY2_REQUEST_HIGHLIGHTED_PATH`)                             |
| F   | 高亮完整路径和名称 (`EVERYTHING_IPC_QUERY2_REQUEST_HIGHLIGHTED_FULL_PATH_AND_NAME`) |

*sort_type* 应该是一个 `EVERYTHING_IPC_SORT_xxx` 常量（数值）。如果没有提供，则默认为 `0`。

*max_results* 允许您限制返回的结果数量。如果没有提供，则默认为 *everything_max_results* 高级偏好设置值。

*offset* 指定结果偏移量。与 *max_results* 结合使用，这允许您查询大型数据集，而无需一次处理所有结果。

*timeout* 指定以毫秒为单位的超时时间。如果没有提供，则默认为 `1000`。
</td></tr><tr><td>
RunCountGet</td><td>

\<string:file\></td><td>

*int*</td><td>
返回指定文件的运行次数。
</td></tr><tr><td>
RunCountInc</td><td>

\<string:file\></td><td>

*int*</td><td>
递增指定文件的运行次数并返回新的次数。
</td></tr><tr><td>
RunCountSet</td><td>

\<string:file\>  
\<int:count\></td><td>

*bool*</td><td>
将指定文件的运行次数设置为提供的值。成功时返回 True。
</td></tr><tr><td>
SendCmd</td><td>

\<int:command\>  
\[\<int:data\>\]</td><td>

*int*</td><td>

向 Everything 发送指定的命令并返回其响应。命令在 Everything API SDK 中有记录（例如，401 等效于 `EVERYTHING_IPC_IS_DB_LOADED` 并返回 1 表示 Everything 的数据库已加载）。
</td></tr><tr><td>
Start</td><td>

*none*</td><td>

*bool*</td><td>
如果 Everything 尚未运行并且 Opus 已配置为自动启动它，则启动 Everything。
</td></tr><tr><td>
Stop</td><td>

*none*</td><td>

*bool*</td><td>
停止 Everything（告诉它退出）。
</td></tr></tbody>
</table>