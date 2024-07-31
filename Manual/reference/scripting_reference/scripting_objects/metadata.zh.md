# Metadata

**Metadata** 对象提供有关文件或文件夹的元数据信息（元数据是指诸如音乐文件的曲目编号、图像的尺寸、文档的作者等信息）。如果您拥有 **Item** 对象，则可以从 **[Item](item.zh.md).metadata** 属性获取 **Metadata** 对象，否则可以使用项目的路径使用 **[FSUtil](fsutil.zh.md).GetMetadata** 方法获取它。

**Metadata** 对象提供不同的子对象作为属性，将可用的元数据分组到多个类别中，大体上对应于 [关键字列](../../metadata_keywords/keywords_for_columns.zh.md) 页面上列出的类别。您可以使用 **Metadata** 对象的 *默认值* 来确定可用的主要元数据类型。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>

返回一个字符串，指示此对象中可用的主要元数据类型。字符串将是以下之一：*none*、*video*、*audio*、*image*、*font*、*exe*、*doc*、*other*。
请注意，有时可能有多种类型的元数据可用。例如，作者是一个文档字段（因此在 **doc** 属性下找到），但图片也可以有作者。在这种情况下，**Metadata** 对象将提供 **ImageMeta** 和 **DocMeta** 对象。

如果返回的字符串是 *none*，则表示该文件没有可用的元数据，您不应该尝试访问任何其它属性。
</td></tr><tr><td>
audio</td><td>

*object*:**[AudioMeta](audiometa.zh.md)**</td><td>

返回一个 **[AudioMeta](audiometa.zh.md)** 对象，提供对音频元数据的访问。此对象的属性通常以其相应的底层类型返回（例如，像“曲目编号”这样的数字字段将作为 *int* 返回）。
</td></tr><tr><td>
audio_text</td><td>

*object*:**[AudioMeta](audiometa.zh.md)**</td><td>

返回一个 **[AudioMeta](audiometa.zh.md)** 对象，提供对未修改的音频元数据文本形式的访问。这提供了与在文件窗口中显示的相同文本的访问。例如，像“曲目编号”这样的数字字段将作为 *string* 而不是 *int* 返回。
</td></tr><tr><td>
doc</td><td>

*object:***[DocMeta](docmeta.zh.md)**</td><td>

返回一个 **[DocMeta](docmeta.zh.md)** 对象，提供对文档元数据的访问。
</td></tr><tr><td>
doc_text</td><td>

*object:***[DocMeta](docmeta.zh.md)**</td><td>

返回一个 **[DocMeta](docmeta.zh.md)** 对象，提供对未修改的文档元数据文本形式的访问。
</td></tr><tr><td>
exe</td><td>

*object:***[ExeMeta](exemeta.zh.md)**</td><td>

返回一个 **[ExeMeta](exemeta.zh.md)** 对象，提供对可执行文件（程序）元数据的访问。
</td></tr><tr><td>
exe_text</td><td>

*object:***[ExeMeta](exemeta.zh.md)**</td><td>

返回一个 **[ExeMeta](exemeta.zh.md)** 对象，提供对未修改的程序元数据文本形式的访问。
</td></tr><tr><td>
font</td><td>

*object:***[FontMeta](fontmeta.zh.md)**</td><td>

返回一个 **[FontMeta](fontmeta.zh.md)** 对象，提供对字体文件元数据的访问。
</td></tr><tr><td>
image</td><td>

*object:***[ImageMeta](imagemeta.zh.md)**</td><td>

返回一个 **[ImageMeta](imagemeta.zh.md)** 对象，提供对图片元数据的访问。
</td></tr><tr><td>
image_text</td><td>

*object:***[ImageMeta](imagemeta.zh.md)**</td><td>

返回一个 **[ImageMeta](imagemeta.zh.md)** 对象，提供对未修改的图片元数据文本形式的访问。
</td></tr><tr><td>
other</td><td>

*object:***[OtherMeta](othermeta.zh.md)**</td><td>

返回一个 **[OtherMeta](othermeta.zh.md)** 对象，提供对杂项元数据的访问。
</td></tr><tr><td>
tags</td><td>

*collection:string*</td><td>

返回一个 *string* 集合，对应于分配给此项目的标签。
</td></tr><tr><td>
video</td><td>

*object:***[VideoMeta](videometa.zh.md)**</td><td>

返回一个 **[VideoMeta](videometa.zh.md)** 对象，提供对视频元数据的访问。
</td></tr><tr><td>
video_text</td><td>

*object:***[VideoMeta](videometa.zh.md)**</td><td>

返回一个 **[VideoMeta](videometa.zh.md)** 对象，提供对未修改的视频元数据文本形式的访问。
</td></tr></tbody>
</table>