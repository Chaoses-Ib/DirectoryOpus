# AudioCoverArt

**AudioCoverArt** 对象提供访问音频文件嵌入式封面图的途径。它可以通过 **[AudioMeta](audiometa.zh.md).coverart** 属性获取。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>

返回一个字符串，指示此封面图的预期用途。可能的值包括 *artist*、*back*、*band*、*bandlogo*、*colorfulfish*（不幸的是，这是 ID3 规范的一部分）、*composer*、*conductor*、*front*、*icon*、*illustration*、*leadartist*、*leaflet*、*location*、*lyricist*、*media*、*other*、*otherfileicon*、*performance*、*publisherlogo*、*recording*、*vidcap*。
</td></tr><tr><td>
data</td><td>

*对象:***[Blob](blob.zh.md)**</td><td>

返回一个 **[Blob](blob.zh.md)** 对象，代表实际的图像数据。
</td></tr><tr><td>
depth</td><td>

*int*</td><td>
返回此图像的位深度。
</td></tr><tr><td>
desc</td><td>

*字符串*</td><td>
返回此图像的描述（如果有）。
</td></tr><tr><td>
ext</td><td>

*字符串*</td><td>
返回此图像的默认文件扩展名，如果可以确定。
</td></tr><tr><td>
height</td><td>

*int*</td><td>
返回此图像的高度，以像素为单位。
</td></tr><tr><td>
mime</td><td>

*字符串*</td><td>
返回图像的 MIME 类型，如果在文件中指定。
</td></tr><tr><td>
size</td><td>

*对象:***[FileSize](filesize.zh.md)**</td><td>

返回一个 **[FileSize](filesize.zh.md)** 对象，代表图像数据的尺寸。
</td></tr><tr><td>
type</td><td>

*字符串*</td><td>

返回预期用途字符串（即 *默认值*）的“漂亮”形式，翻译成当前 Opus 用户界面语言。
</td></tr><tr><td>
width</td><td>

*int*</td><td>
返回此图像的宽度，以像素为单位。
</td></tr></tbody>
</table>