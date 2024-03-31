**AudioCoverArt** 对象提供对音频文件嵌入封面的访问。可以通过 **[AudioMeta](audiometa.zh.md).coverart** 属性获取它。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*<默认值>*</td><td>

*字符串*</td><td>

返回一个字符串，表示此封面的预期用途。可能的值有： *artist*、*back*、*band*、*bandlogo*、*colofulfish*（不幸的是这是 ID3 规范的一部分）、*composer*、*conductor*、*front*、*icon*、*illustration*、*leadartist*、*leaflet*、*location*、*lyricist*、*media*、*other*、*otherfileicon*、*performance*、*publisherlogo*、*recording*、*vidcap*。
</td></tr><tr><td>
data</td><td>

*对象：***[Blob](blob.zh.md)**</td><td>

返回一个 **[Blob](blob.zh.md)** 对象，表示实际的图像数据。
</td></tr><tr><td>
depth</td><td>

*整数*</td><td>
返回此图像的比特深度。
</td></tr><tr><td>
desc</td><td>

*字符串*</td><td>
返回此图像的说明（如果有）。
</td></tr><tr><td>
ext</td><td>

*字符串*</td><td>
如果能确定，则返回此图像的默认文件扩展名。
</td></tr><tr><td>
height</td><td>

*整数*</td><td>
返回此图像的高度（以像素为单位）。
</td></tr><tr><td>
mime</td><td>

*字符串*</td><td>
如果文件中指定，则返回图像的 MIME 类型。
</td></tr><tr><td>
size</td><td>

*对象：***[FileSize](filesize.zh.md)**</td><td>

返回一个 **[FileSize](filesize.zh.md)** 对象，表示图像数据的大小。
</td></tr><tr><td>
type</td><td>

*字符串*</td><td>

返回一个“漂亮”的预期用途字符串形式（即 *默认值*），并翻译为当前 Opus 用户界面语言。
</td></tr><tr><td>
width</td><td>

*整数*</td><td>
返回此图像的宽度（以像素为单位）。
</td></tr></tbody>
</table>