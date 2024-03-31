# 元数据的编程设置

使用 **[SetAttr](/Manual/reference/command_reference/internal_commands/setattr.zh.md) META** 命令可以自动更改文件元数据。

![](/Manual/images/media/13/star_rating_menu.png)

例如，您可以创建一个菜单，以便对文件应用不同的评级。

此菜单是由六个不同的命令创建的，每个命令将不同的评级应用于选定的文件。

- 清除评级的命令为 `SetAttr META rating:0`
- 1 星的命令为 `SetAttr META rating:1`
- 2 星的命令为 `SetAttr META rating:2`（依此类推。）

此命令的一般模板为：

`SetAttr META 关键字:<值> 关键字:<值> ...`

您可以在命令行上指定任意数量的 ***关键字:**\<值\>* 对。关键字必须是 [Keywords for SetAttr META](/Manual/reference/metadata_keywords/keywords_for_setattr_meta.zh.md) 页面上列出的元数据关键字之一。*\<值\>* 会根据您设置的字段而有所不同。

如果缺少 *\<值\>* 部分，则会清除指定的关键字。例如，

`SetAttr META album`

重要的是要记住，如果 *\<值\>* 含有任何嵌入空格，则必须用引号括起整个 ***关键字:**\<值\>* 对。例如，

`SetAttr META "album:Dark Side Of The Moon" "albumartist:Pink Floyd"`

指定的关键字还可以包含 [通配符](/Manual/reference/wildcard_reference/pattern_matching_syntax.zh.md)，以便立即将相同的值应用于多个元数据字段。例如，您可以使用 **\*artist** 一次性设置 **artist**、**albumartist** 和 **origartist** 字段。您还可以使用此方法清除所有元数据字段：

`SetAttr META`

一些元数据值支持比简单字符串更复杂的数据。例如，您可以对 EXIF *拍摄日期* 字段应用偏移量，以调整当前值，而不是完全替换它。要减去一个小时，命令应为：

`SetAttr META datetaken:-1`

有关关键字及其可接受值的完整列表，请参阅 [Keywords for SetAttr META](/Manual/reference/metadata_keywords/keywords_for_setattr_meta.zh.md) 页面。

您还可以使用 **copyfrom** 关键字，从源文件将某些元数据组合复制到目标文件。其模板为：

`SetAttr META copyfrom:<类型>,<文件名>`

在上面，*\<类型\>* 是一个数字值，表示应复制何种类型的属性。*\<类型\>* 的可用值包括：

| 类型 | 类别  | 复制内容                                              |
|------|-----------|------------------------------------------------------------|
| 1    | 音乐     | 艺术家、专辑、年份、流派                                  |
| 2    | 音乐     | 除标题和曲目以外的所有内容                                |
| 3    | 音乐     | 全部                                                        |
| 4    | 文档     | 作者和所有权                                              |
| 5    | 文档     | 除标题和主题以外的所有内容                                |
| 6    | 文档     | 全部                                                        |
| 7    | 电影     | 导演、制片人、编剧                                      |
| 8    | 电影     | 除标题以外的所有内容                                    |
| 9    | 电影     | 全部                                                        |
| 10   | 图片     | 作者和所有权                                              |
| 11   | 图片     | GPS                                                         |
| 12   | 图片     | GPS 和相机                                                 |
| 13   | 图片     | 作者、所有权、相机                                    |
| 14   | 图片     | 作者、所有权、GPS                                        |
| 15   | 图片     | 全部                                                        |

*\<文件\>* 是要从中复制指定元数据的源文件。请记住，如果文件名包含空格，则必须用引号括起 ***关键字:**\<值\>* 对。例如，

`SetATTR META "copyfrom:8,/myvideos/my home movie1.avi"`