# Column 关键字

**[Set](../command_reference/internal_commands/set.zh.md)** 命令（带有 **COLUMNS**, **COLUMNSADD**, **COLUMNSREMOVE** 和 **COLUMNSTOGGLE** 参数）使用以下关键字来更改文件列表中显示的列（在详细信息和高级模式中），并且使用 **GROUPBY** 和 **SORTBY** 参数来修改组和排序字段。例如，**Set COLUMNSADD=desc** 将 Description 列添加到文件列表中。

当 [使用元数据重命名](/Manual/file_operations/renaming_files/advanced_rename/renaming_with_metadata.zh.md) 时，[重命名](/Manual/file_operations/renaming_files/README.zh.md) 功能和定义您自己的 [平铺](/Manual/file_types/filetype_editor/tiles_mode.zh.md) 和 [信息提示](/Manual/file_types/filetype_editor/info_tip.zh.md) 定义时，[文件类型](/Manual/file_types/filetype_editor/README.zh.md) 编辑器也会使用这些关键字。

请注意，某些列出现在多个类别中。由于历史原因，列关键字有时仅反映狭窄的用法，而实际上该列适用于更广泛的情况。例如，*Duration* 列 (**mp3songlength**) 适用于各种音乐文件类型，以及某些电影类型，而不仅仅是 MP3 音乐文件。

当列用于输出文本（例如，在为重命名生成文件名或显示信息提示时），可以覆盖日期、时间和数值的格式。

### 日期和时间字段

日期和时间字段允许你配置日期格式、时间格式或两者。例如，

|                                   |                                                                              |
|-----------------------------------|------------------------------------------------------------------------------|
| **{datetaken\|D#yyyy-MM-dd}**     | 插入仅为 **yyyy-MM-dd** 格式的日期（例如 *2023-09-22*）           |
| **{modified\|T#HH-mm-ss}**        | 以 **HH-mm-ss** 格式插入修改时间（例如 *13:10:55*）           |
| **{datetaken\|A#yyyyMMddHHmmss}** | 将日期和时间同时插入为 **yyyyMMddHHmmss**（例如 *20221130154410*） |

如你从示例中看到，**D#** 用于标记日期格式，**T#** 用于标记时间格式，**A#** 表示日期和时间代码均存在。有关日期和时间格式的信息，请参阅 [日期和时间代码](../command_reference/external_control_codes/codes_for_date_and_time.zh.md) 页面。

### 数值字段

数值字段允许你控制零填充。例如，

|                    |                                                               |
|--------------------|---------------------------------------------------------------|
| **{size\|#8}**     | 将字节大小零填充为八位（例如 *00045412*） |
| **{mp3track\|#2}** | 将曲目号零填充为两位（例如 *08*）          |

文件名可以使用 **{name\|noext}** 检索，而无需文件扩展名。

------------------------------------------------------------------------

## 列关键字

### 日期和时间

<table>
<thead><tr><th>
列</th><th>
关键字
</th></tr></thead><tbody><tr><td>
创建（相对）</td><td>
cdaterel
</td></tr><tr><td>
日期（访问）</td><td>
accesseddate
</td></tr><tr><td>
日期（创建）</td><td>
createddate
</td></tr><tr><td>
日期（修改）</td><td>
modifieddate
</td></tr><tr><td>
日期和时间（访问）</td><td>
accessed
</td></tr><tr><td>
日期和时间（创建）</td><td>
created
</td></tr><tr><td>
日期和时间（修改）</td><td>
modified
</td></tr><tr><td>
修改（相对）</td><td>
daterel
</td></tr><tr><td>
时间（访问）</td><td>
accessedtime
</td></tr><tr><td>
时间（创建）</td><td>
createdtime
</td></tr><tr><td>
时间（修改）</td><td>
modifiedtime
</td></tr></tbody>
</table>

### 文档

<table>
<thead><tr><th>
列</th><th>
关键字
</th></tr></thead><tbody><tr><td>
作者</td><td>
author
</td></tr><tr><td>
类别</td><td>
category
</td></tr><tr><td>
注释</td><td>
comments
</td></tr><tr><td>
公司</td><td>
companyname
</td></tr><tr><td>
版权</td><td>
copyright
</td></tr><tr><td>
创建者</td><td>
creator
</td></tr><tr><td>
文档创建日期</td><td>
doccreateddate
</td></tr><tr><td>
最后编辑时间</td><td>
docedittime
</td></tr><tr><td>
最后保存者</td><td>
doclastsavedby
</td></tr><tr><td>
最后保存日期</td><td>
doclastsaveddate
</td></tr><tr><td>
页数</td><td>
pages
</td></tr><tr><td>
生成器</td><td>
producer
</td></tr><tr><td>
主题</td><td>
subject
</td></tr><tr><td>
标题</td><td>
title
</td></tr></tbody>
</table>

### 名称和路径

<table>
<thead><tr><th>
列</th><th>
关键字
</th></tr></thead><tbody><tr><td>
扩展名</td><td>
ext
</td></tr><tr><td>
扩展名（目录）</td><td>
extdir
</td></tr><tr><td>
文件名</td><td>
name
</td></tr><tr><td>
完整路径</td><td>
fullpath
</td></tr><tr><td>
位置</td><td>
path
</td></tr><tr><td>
位置（相对）</td><td>
pathrel
</td></tr><tr><td>
父文件夹</td><td>
parent
</td></tr><tr><td>
父文件夹（完整）</td><td>
parentlocation
</td></tr><tr><td>
父位置</td><td>
parentpath
</td></tr><tr><td>
路径长度</td><td>
pathlen
</td></tr><tr><td>
短名称</td><td>
shortname
</td></tr></tbody>
</table>

### 图片尺寸

<table>
<thead><tr><th>
列</th><th>
关键字
</th></tr></thead><tbody><tr><td>
宽高比</td><td>
aspectratio
</td></tr><tr><td>
位深</td><td>
picdepth
</td></tr><tr><td>
尺寸</td><td>

picsize  
dimensions
</td></tr><tr><td>
高度</td><td>
picheight
</td></tr><tr><td>
物理高度</td><td>
picphysy
</td></tr><tr><td>
物理大小</td><td>
picphyssize
</td></tr><tr><td>
物理宽度</td><td>
picphysx
</td></tr><tr><td>
分辨率（X）</td><td>
picresx
</td></tr><tr><td>
分辨率（Y）</td><td>
picresy
</td></tr><tr><td>
旋转</td><td>
rotation
</td></tr><tr><td>
宽度</td><td>
picwidth
</td></tr></tbody>
</table>

### 图片元数据

<table>
<thead><tr><th>
列</th><th>
关键字
</th></tr></thead><tbody><tr><td>
海拔</td><td>
altitude
</td></tr><tr><td>
光圈</td><td>
apertureval
</td></tr><tr><td>
艺术家</td><td>
mp3artist
</td></tr><tr><td>
相机制造商</td><td>
cameramake
</td></tr><tr><td>
相机型号</td><td>
cameramodel
</td></tr><tr><td>
色彩模型</td><td>
colormodel
</td></tr><tr><td>
对比度</td><td>
contrast
</td></tr><tr><td>
坐标</td><td>
coords
</td></tr><tr><td>
版权</td><td>
copyright
</td></tr><tr><td>
创建软件</td><td>
software
</td></tr><tr><td>
数字化日期</td><td>
datedigitized
</td></tr><tr><td>
拍摄日期</td><td>

datetaken  
shootingtime
</td></tr><tr><td>
数码变焦</td><td>
digitalzoom
</td></tr><tr><td>
曝光补偿</td><td>
exposurebias
</td></tr><tr><td>
曝光程序</td><td>
exposureprogram
</td></tr><tr><td>
曝光时间</td><td>
exposuretime
</td></tr><tr><td>
F 值</td><td>
fnumber
</td></tr><tr><td>
闪光灯</td><td>
flash
</td></tr><tr><td>
焦距</td><td>
focallength
</td></tr><tr><td>
35mm 焦距</td><td>
35mmfocallength
</td></tr><tr><td>
ISO 速度</td><td>
isorating
</td></tr><tr><td>
图像描述</td><td>
</td></tr><tr><td>
图像质量</td><td>
imagequality
</td></tr><tr><td>
纬度</td><td>
latitude
</td></tr><tr><td>
镜头制造商</td><td>
lensmake
</td></tr><tr><td>
镜头型号</td><td>
lensmodel
</td></tr><tr><td>
经度</td><td>
longitude
</td></tr><tr><td>
微距模式</td><td>
macromode
</td></tr><tr><td>
计量模式</td><td>
meteringmode
</td></tr><tr><td>
饱和度</td><td>
saturation
</td></tr><tr><td>
场景捕获类型</td><td>
scenecapturetype
</td></tr><tr><td>
场景模式</td><td>
scenemode
</td></tr><tr><td>
清晰度</td><td>
sharpness
</td></tr><tr><td>
快门速度</td><td>
shutterspeed
</td></tr><tr><td>
主题</td><td>
subject
</td></tr><tr><td>
主体距离</td><td>
subjectdistance
</td></tr><tr><td>
特殊说明</td><td>
instructions
</td></tr><tr><td>
标题</td><td>
title
</td></tr><tr><td>
白平衡</td><td>
whitebalance
</td></tr></tbody>
</table>

### 程序

<table>
<thead><tr><th>
列</th><th>
关键词
</th></tr></thead><tbody><tr><td>
版权</td><td>
copyright
</td></tr><tr><td>
公司</td><td>
companyname
</td></tr><tr><td>
模块说明</td><td>
moddesc
</td></tr><tr><td>
模块版本</td><td>
modversion
</td></tr><tr><td>
产品名称</td><td>
prodname
</td></tr><tr><td>
产品版本</td><td>
prodversion
</td></tr></tbody>
</table>

### 文件大小

<table>
<thead><tr><th>
列</th><th>
关键词
</th></tr></thead><tbody><tr><td>
大小（KB）</td><td>
sizekb
</td></tr><tr><td>
大小（自动）</td><td>
sizeauto
</td></tr><tr><td>
大小（字节）</td><td>
size
</td></tr><tr><td>
大小（相对）</td><td>
sizerel
</td></tr><tr><td>
磁盘上的大小（KB）</td><td>
disksizekb
</td></tr><tr><td>
磁盘上的大小（自动）</td><td>
disksizeauto
</td></tr><tr><td>
磁盘上的大小（字节）</td><td>
disksize
</td></tr><tr><td>
磁盘上的大小（相对）</td><td>
disksizerel
</td></tr><tr><td>
未压缩大小</td><td>
uncompressedsize
</td></tr></tbody>
</table>

### 常规

<table>
<thead><tr><th>
列</th><th>
关键词
</th></tr></thead><tbody><tr><td>
属性</td><td>
attr
</td></tr><tr><td>
可用性</td><td>
availability
</td></tr><tr><td>
说明</td><td>
desc
</td></tr><tr><td>
文件计数</td><td>
filecount
</td></tr><tr><td>
字体名称</td><td>
fontname
</td></tr><tr><td>
组</td><td>
group
</td></tr><tr><td>
索引</td><td>
index
</td></tr><tr><td>
标签</td><td>
label
</td></tr><tr><td>
MD5 校验和</td><td>
md5sum
</td></tr><tr><td>
所有者</td><td>
owner
</td></tr><tr><td>
评级</td><td>
rating
</td></tr><tr><td>
SHA-1 校验和</td><td>
shasum
</td></tr><tr><td>
状态图标</td><td>
status
</td></tr><tr><td>
子文件夹计数</td><td>
dircount
</td></tr><tr><td>
标签</td><td>
keywords
</td></tr><tr><td>
目标</td><td>
target
</td></tr><tr><td>
缩略图</td><td>
thumbnail
</td></tr><tr><td>
文件计数总计</td><td>
filecounttotal
</td></tr><tr><td>
子文件夹计数总计</td><td>
dircounttotal
</td></tr><tr><td>
类型</td><td>
type
</td></tr><tr><td>
用户说明</td><td>
userdesc
</td></tr></tbody>
</table>

### 电影

<table>
<thead><tr><th>
列</th><th>
关键词
</th></tr></thead><tbody><tr><td>
纵横比</td><td>
aspectratio
</td></tr><tr><td>
音频编解码器</td><td>

audiocodec  
mp3type
</td></tr><tr><td>
位深度</td><td>
picdepth
</td></tr><tr><td>
比特率</td><td>
mp3bitrate
</td></tr><tr><td>
播出日期</td><td>
broadcastdate
</td></tr><tr><td>
频道号</td><td>
channel
</td></tr><tr><td>
工作人员表</td><td>
credits
</td></tr><tr><td>
数据速率</td><td>
datarate
</td></tr><tr><td>
尺寸</td><td>

picsize  
dimensions
</td></tr><tr><td>
持续时间</td><td>

duration  
mp3songlength
</td></tr><tr><td>
剧集名称</td><td>
episodename
</td></tr><tr><td>
FOURCC 代码</td><td>
fourcc
</td></tr><tr><td>
帧率</td><td>
framerate
</td></tr><tr><td>
高度</td><td>
picheight
</td></tr><tr><td>
高清？</td><td>
ishd
</td></tr><tr><td>
模式</td><td>
mp3mode
</td></tr><tr><td>
物理大小</td><td>
picphyssize
</td></tr><tr><td>
发行商</td><td>
publisher
</td></tr><tr><td>
录制时间</td><td>
recordingtime
</td></tr><tr><td>
重复？</td><td>
isrepeat
</td></tr><tr><td>
采样率</td><td>
mp3samplerate
</td></tr><tr><td>
电台名称</td><td>
station
</td></tr><tr><td>
视频编解码器</td><td>
videocodec
</td></tr><tr><td>
宽度</td><td>
picwidth
</td></tr></tbody>
</table>

### 音乐

<table>
<thead><tr><th>
列</th><th>
关键词
</th></tr></thead><tbody><tr><td>
专辑</td><td>
mp3album
</td></tr><tr><td>
专辑艺术家</td><td>
mp3albumartist
</td></tr><tr><td>
艺术家</td><td>
mp3artist
</td></tr><tr><td>
音频编解码器</td><td>

audiocodec  
mp3type
</td></tr><tr><td>
BPM</td><td>
mp3bpm
</td></tr><tr><td>
位深度</td><td>
picdepth
</td></tr><tr><td>
比特率</td><td>
mp3bitrate
</td></tr><tr><td>
合辑</td><td>
compilation
</td></tr><tr><td>
作曲者</td><td>
composers
</td></tr><tr><td>
指挥者</td><td>
conductors
</td></tr><tr><td>
版权</td><td>
copyright
</td></tr><tr><td>
光盘号</td><td>

mp3disc  
mp3disk
</td></tr><tr><td>
持续时间</td><td>
mp3songlength
</td></tr><tr><td>
编码者</td><td>
mp3encoder
</td></tr><tr><td>
编码软件</td><td>
mp3encodingsoftware
</td></tr><tr><td>
流派</td><td>
mp3genre
</td></tr><tr><td>
首调</td><td>
initialkey
</td></tr><tr><td>
模式</td><td>
mp3mode
</td></tr><tr><td>
音乐备注</td><td>
mp3comment
</td></tr><tr><td>
音乐信息</td><td>
mp3info
</td></tr><tr><td>
音乐标题</td><td>
mp3title
</td></tr><tr><td>
受保护</td><td>
mp3drm
</td></tr><tr><td>
发行日期</td><td>
releasedate
</td></tr><tr><td>
采样率</td><td>
mp3samplerate
</td></tr><tr><td>
音轨号</td><td>
mp3track
</td></tr><tr><td>
年</td><td>
mp3year
</td></tr></tbody>
</table>

你还可以使用上述标准列集的一部分之外的某些列。这些列来自不同的位置 - 第三方 Shell 命名空间扩展可以提供自定义列，Opus 插件也可以这样做。此外，Zip 和 FTP 还定义了几列，这些列只在这些类型的文件夹中有效。在 Opus 中，这些列都显示在 **其他** 类别下。为了从命令中引用这些列之一，你需要知道该列的名称，然后使用适当的前缀来指示要使用特殊列。

![](/Manual/images/media/special_columns.png) 

在 Opus 中， Shell 扩展提供的列（如上图所示）加 **sh:** 为前缀 - 该列的关键词是列表中显示的名称，不带空格。

例如，要添加 **SVN Status** 列，你可以使用命令 **Set COLUMNSADD sh:svnstatus**。

必须使用插件 DLL 名称（例如 **opus7zip:packed**）作为前缀接入插件（例如 7-Zip 插件）。

Opus 提供以下列关键词，但只在特定文件夹中有效：

- *FTP* 关键词只在 **ftp://** 路径中有效
- *Zip* 关键词只在查看 Zip 压缩包时有效
- *7-Zip* 关键词只在查看由 7-Zip 插件处理的压缩包时有效
- *Computer* 关键词只在查看 [native Computer 文件夹](/Manual/basic_concepts/virtual_file_system/system_virtual_folders.zh.md) 时有效
<table>
<thead><tr><th>
列</th><th>
**关键字**
</th></tr></thead><tbody><tr><td>

\$ **FTP 关键字**</td><td>
传输时间
</td></tr><tr><td>
<ftp:xfertime></td><td>
组
</td></tr><tr><td>
<ftp:group></td><td>

\$ **计算机关键字**
</td></tr><tr><td>
驱动器上的空闲空间</td><td>
sh:freespace
</td></tr><tr><td>
文件系统</td><td>
sh:filesys
</td></tr><tr><td>
已用空间（图形）</td><td>
sh:usedpercent
</td></tr><tr><td>
空闲空间（图形）</td><td>
sh:freepercent
</td></tr><tr><td>
网络位置</td><td>
sh:netlocation
</td></tr><tr><td>
驱动器上的已用空间</td><td>
sh:usedspace
</td></tr><tr><td>

\$ **Zip 关键字**</td><td>
已压缩大小
</td></tr><tr><td>
zip:compsize</td><td>
压缩率
</td></tr><tr><td>
zip:compratio</td><td>
压缩方法
</td></tr><tr><td>
zip:compmethod</td><td>
CRC 校验和</td></tr><tr><td>
zip:compcrc</td><td>

\$ **7-Zip 关键字**</td></tr><tr><td>
已打包大小</td><td>
opus7zip:packed
</td></tr><tr><td>
比率</td><td>
opus7zip:ratio
</td></tr><tr><td>
CRC</td><td>
opus7zip:crc
</td></tr><tr><td>
块</td><td>
opus7zip:block
</td></tr><tr><td>
索引</td><td>
opus7zip:index
</td></tr><tr><td>
是否为实体？</td><td>
opus7zip:solid
</td></tr><tr><td>
方法</td><td>
opus7zip:method
</td></tr><tr><td>
模式</td><td>
opus7zip:mode
</td></tr><tr><td>
链接</td><td>
opus7zip:link
</td></tr><tr><td>
用户</td><td>
opus7zip:user
</td></tr><tr><td>
组</td><td>
opus7zip:group
</td></tr></tbody>
</table>