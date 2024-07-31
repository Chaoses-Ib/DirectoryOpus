# AudioMeta

**AudioMeta** 对象可以通过 **[Metadata](metadata.zh.md).audio** 或 **[Metadata](metadata.zh.md).audio_text** 属性获取。它提供了访问与音频文件相关的元数据的途径。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<column keyword\>*</td><td>

*variant*</td><td>

返回指定列的值，如 [列关键词](../../metadata_keywords/keywords_for_columns.zh.md) 页面 *音乐* 部分所列。
</td></tr><tr><td>
coverart</td><td>

*collection:***[AudioCoverArt](audiocoverart.zh.md)**</td><td>

返回一个包含 **[AudioCoverArt](audiocoverart.zh.md)** 对象的集合，这些对象代表存储在音频文件中的任何封面图像。

此属性的默认值返回封面图像的数量 - 出于性能原因，您应该在枚举或访问集合中的单个项目之前检查它是否大于 0。
</td></tr></tbody>
</table>