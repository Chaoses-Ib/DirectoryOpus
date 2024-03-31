**AudioMeta** 对象从 **[Metadata](metadata.zh.md).audio** 或 **[Metadata](metadata.zh.md).audio_text** 属性检索。它提供对与声音文件相关的元数据的访问。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<column keyword\>*</td><td>

*variant*</td><td>

返回指定的列的值，如 [列关键字](../../metadata_keywords/keywords_for_columns.zh.md) 页面上的 *音乐* 部分所列。
</td></tr><tr><td>
coverart</td><td>

*集合:***[AudioCoverArt](audiocoverart.zh.md)**</td><td>

返回一个代表存储在音频文件中的任何图片封面的 **[AudioCoverArt](audiocoverart.zh.md)** 对象的集合。

此属性的默认值返回图片封面的数目 - 出于性能的原因，应在枚举集合中的单个项或访问它们前检查这个值是否大于 0。
</td></tr></tbody>
</table>