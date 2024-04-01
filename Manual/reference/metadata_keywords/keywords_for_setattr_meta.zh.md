# SetAttr META 的关键字

使用 **[SetAttr](../command_reference/internal_commands/setattr.zh.md) META** 命令可以修改文件元数据 [按程序](/Manual/file_operations/editing_metadata/programmatic_setting_of_metadata.zh.md)。大多数字段都可以设置为字符串（或数字），或清空，但是有些字段接受更加复杂的指令，如下说明。

<table>
<thead><tr><th>
字段</th><th>
关键字</th><th>
说明
</th></tr></thead><tbody><tr><td>

**标准属性**</td><td>
</td><td>

</td></tr><tr><td>
属性</td><td>
attr</td><td>

属性被指定为以下一个或多个字母:  
**A** (档案)  
**R** (只读)  
**H** (隐藏)  
**S** (系统)  
**C** (压缩)  
**E** (加密)

你还可以使用 **+** 来开启属性，使用 **-** 来关闭属性。

//<示例://>

**SetAttr META attr:+c-r***   - 设置压缩属性并清除只读属性*
</td></tr><tr><td>
创建日期</td><td>
createdate</td><td>

日期和时间可以被设置为绝对日期（在这种情况下，时间将不会改变），绝对时间（在这种情况下，日期将不会改变），或两者。  
绝对时间和日期的接受的格式为：  
**YYYY-MM-DD** - 仅设置日期  
**HH:MM:SS** - 仅设置时间  
**YYYY-MM-DD HH:MM:SS** - 设置时间和日期（需要引号）  
关键字 **now** 也能用于使用当前日期和时间。  
你还可以对当前日期和时间设置进行相对调整，使用以下格式：  
**\<time-adjust\> ** - 仅调整时间  
**\<date-adjust\> \<time-adjust\>**  - 调整日期和时间（需要引号）

**\<time-adjust\>** 字符串的有效格式为：  
**\[+-\]H:M:S**  - 添加或减去小时、分和秒  
**\[+-\]H:M**  - 添加或减去小时和分数  
**\[+-\]H**  - 添加或减去小时数  
**\<date-adjust\>** 字符串的有效格式为：  
**\[+-\]Y:M:D**  - 添加或减去年、月和日值  
**\[+-\]M:D**  - 添加或减去月和日值  
**\[+-\]D**  - 添加或减去天数

你不能不调整时间而调整日期，所以如果你只想调整日期，就为 *\<time-adjust\>* 指定0。

*示例*：

**SetAttr META createdate:now***   - 将创建日期设置为当前日期/时间*  
**SetAttr META createdate:20100922***   - 将创建日期设置为 2010年 9 月 22 日*  
**SetAttr META "createdate:20100922 15:30:30"***   - 也将时间设置为下午 3:30*  
**SetAttr META createdate:+1:30***   - 将 1 小时 30 分钟添加到创建时间*  
**SetAttr META "createdate:+1 0"***   - 添加 1 天（和零小时）*

你还可以通过指定另一个字段的名称来从另一个日期字段复制值：**createdate**、**lastmodifieddate**、**datedigitized** 或 **datetaken**。（出于向后兼容性考虑，**modifydate** 也作为 **lastmodifieddate** 的别名。）

*示例*：

**SetAttr META createdate:lastmodifieddate***   - 将创建日期设置为文件的最后修改日期/时间*
</td></tr><tr><td>
修改日期</td><td>
lastmodifieddate</td><td>

接受与 **createdate** 相同的值（如上所述）。
</td></tr><tr><td>

**  
扩展属性**</td><td>
</td><td>

</td></tr><tr><td>
备注</td><td>

comment  
usercomment</td><td>
用户定义的字符串。
</td></tr><tr><td>
评分</td><td>
rating</td><td>

接受 **0**（以清除评分）到 **5**（5 颗星）的值。
</td></tr><tr><td>
标签</td><td>
tags</td><td>

接受多个用分号分隔的标签。你可以绝对地设置标签，或向现有标签集添加标签或移除标签。

*示例*：

**SetAttr META tags:one;two***   - 将标签设置为“one”和“two”*  
**SetAttr META tags:+one***   - 向任何现有标签添加标签“one”*  
**SetAttr META tags:+one;-two***   - 添加“one”并移除“two”*
</td></tr><tr><td>

**  
图片属性**</td><td>
</td><td>

</td></tr><tr><td>
孔径</td><td>
aperture</td><td>
接受十进制或分数。
</td></tr><tr><td>
相机制造商</td><td>
cameramake</td><td>
用户定义的字符串。
</td></tr><tr><td>
相机型号</td><td>
cameramodel</td><td>
用户定义的字符串。
</td></tr><tr><td>
对比度</td><td>
contrast</td><td>

接受以下值（可以使用 *值* 或 *关键词*）：

\<WRAP\>

| 值 | 关键词 |
|-------|---------|
| 0     | normal  |
| 1     | soft    |
| 2     | hard    |

\</WRAP\>\<wrap clear/\>

//<示例://>

**SetAttr META contrast:2**
</td></tr><tr><td>
创建软件</td><td>
software</td><td>
用户定义的字符串。
</td></tr><tr><td>
数字化日期</td><td>
datedigitized</td><td>

接受与 **createdate** 相同的值（如 **标准属性** 部分中所述）。
</td></tr><tr><td>
拍摄日期</td><td>
datetaken</td><td>

接受与 **createdate** 相同的值（如 **标准属性** 部分中所述）。
</td></tr><tr><td>
数码变焦</td><td>
digitalzoom</td><td>

接受十进制或分数，以及关键词 **off**。
</td></tr><tr><td>
曝光补偿</td><td>
exposurebias</td><td>
接受十进制或分数。
</td></tr><tr><td>
曝光程序</td><td>
exposureprogram</td><td>

接受以下值（可以使用 *值* 或 *关键词*）：  
\<WRAP\>

  
^值^关键词^

|     |                  |
|-----|------------------|
| 0   | notdefined       |
| 1   | manual           |
| 2   | auto             |
| 3   | aperturepriority |
| 4   | shutterpriority  |
| 5   | creativeprogram  |
| 6   | actionprogram    |
| 7   | portraitmode     |
| 8   | landscapemode    |

\</WRAP\>\<wrap clear/\>

*示例*：

**SetAttr META exposureprogram:aperturepriority**
</td></tr><tr><td>
曝光时间</td><td>
exposuretime</td><td>

以秒或几分之一秒指定 - 接受十进制或分数。
</td></tr><tr><td>
F 数</td><td>
fnumber</td><td>
接受十进制或分数。
</td></tr><tr><td>
闪光灯</td><td>
flash</td><td>

接受以下值（可以使用 *值* 或 *关键词*）：
\<WRAP\>

  
^值^关键词^

|      |                                                        |
|------|--------------------------------------------------------|
| 0x00 | noflash                                                |
| 0x01 | fired                                                  |
| 0x05 | fired,strobereturnlightnotdetected                     |
| 0x07 | fired,strobereturnlightdetected                        |
| 0x08 | yes,didnotfire                                         |
| 0x09 | yes,compulsory                                         |
| 0x0d | yes,compulsory,returnlightnotdetected                  |
| 0x0f | yes,compulsory,returnlightdetected                     |
| 0x10 | no,compulsory                                          |
| 0x14 | no,didnotfire,returnnotdetected                        |
| 0x18 | no,auto                                                |
| 0x19 | yes,auto                                               |
| 0x1d | yes,auto,returnlightnotdetected                        |
| 0x1f | yes,auto,returnlightdetected                           |
| 0x20 | noflashfunction                                        |
| 0x41 | yes,red-eyereduction                                   |
| 0x45 | yes,red-eyereduction,returnlightnotdetected            |
| 0x47 | yes,red-eyereduction,returnlightdetected               |
| 0x49 | yes,compulsory,red-eyereduction                        |
| 0x4d | yes,compulsory,red-eyereduction,returnlightnotdetected |
| 0x4f | yes,compulsory,red-eyereduction,returnlightdetected    |
| 0x50 | no,red-eyereduction                                    |
| 0x58 | no,auto,red-eyereduction                               |
| 0x59 | yes,auto,red-eyereduction                              |
| 0x5d | yes,auto,red-eyereduction,returnlightnotdetected       |
| 0x5f | yes,auto,red-eyereduction,returnlightdetected          |

\</WRAP\>\<wrap clear/\>

或者，可以联合使用以下代码来表示不同的状态：

- **Y**: 闪光已触发。
- **N**: 闪光未触发。
- **S\[yn-\]**: 闪光灯返回；**y**: 检测到，**n**: 未检测到，**-**: 不存在
- **C\[yna\]**: 强制；**y**: 是，**n**: 否，**a**: 自动
- **P\[yn\]**: 闪光灯存在；**y**: 是，**n**: 否
- **R\[yn\]**: 红眼消除；**y**: 是，**n**: 否

//<示例://>

**SetAttr META flash:0x50  
SetAttr META flash:yes,auto,red-eyereduction  
SetAttr META flash:YCaRy**
</td></tr><tr><td>
焦距</td><td>
focallength</td><td>

以毫米为单位指定 - 接受十进制或分数。
</td></tr><tr><td>
焦距 (35mm)</td><td>
35mmfocallength</td><td>

以毫米为单位指定 - 接受十进制或分数。
</td></tr><tr><td>
GPS 海拔高度</td><td>
gpsaltitude</td><td>

指定为相对于海平面的米数 - 接受十进制或分数。要指定海平面以下，则指定一个负数。

//<示例://>

**SetAttr META gpsaltitude:-423**
</td></tr><tr><td>
GPS 纬度</td><td>
gpslatitude</td><td>

接受以下任何格式的坐标：  
\<WRAP\>

  
\|45:26:46N\|

|               |
|---------------|
| 45:26:46.302N |
| 45N26 21      |
| 45.446195N    |
| 45.446195     |
| N45° 26.7717' |
| 45°26'21"N    |

\</WRAP\>\<wrap clear/\>

//<示例://>

**SetAttr META gpslatitude:45:26:46.302N**
</td></tr><tr><td>
GPS 经度</td><td>
gpslongitude</td><td>

接受以下任何格式的坐标：  
\<WRAP\>

  
\|65:56:55W\|

|                |
|----------------|
| 65:56:55.903W  |
| 65W58 36       |
| 65.948862W     |
| -65.948862     |
| W65° 56.93172' |
| 65°58'36"W     |

\</WRAP\>\<wrap clear/\>

//<示例://>

**SetAttr META gpslongitude:65W58.36**
</td></tr><tr><td>
图像描述</td><td>
imagedesc</td><td>
用户自定义字符串。
</td></tr><tr><td>
ISO 速度</td><td>
isospeed</td><td>
接受数值。
</td></tr><tr><td>
测光模式</td><td>
meteringmode</td><td>

接受以下值（可以使用 *值* 或 *关键词*）：  
\<WRAP\>

  
^Value^Keyword^

|     |                       |
|-----|-----------------------|
| 0   | unknown               |
| 1   | average               |
| 2   | centerweightedaverage |
| 3   | spot                  |
| 4   | multi-spot            |
| 5   | multi-segment         |
| 6   | partial               |
| 255 | other                 |

\</WRAP\>\<wrap clear/\>
</td></tr><tr><td>
旋转</td><td>
orientation</td><td>

接受 **0**、**90**、**180** 和 **270** 的值。  
还可以接受增量值来调整现有方向值。

//<示例://>

**SetAttr META orientation:90***   - 设置方向为 90*  
**SetAttr META orientation:-90***   - 逆时针旋转方向 90 度*
</td></tr><tr><td>
饱和度</td><td>
saturation</td><td>

接受以下值（可以使用 *值* 或 *关键词*）：

\<WRAP\>

  
^Value^Keyword^

|     |        |
|-----|--------|
| 0   | normal |
| 1   | low    |
| 2   | high   |

\</WRAP\>\<wrap clear/\>
</td></tr><tr><td>
场景捕获类型</td><td>
scenecapturetype</td><td>

接受以下值（可以使用 *值* 或 *关键词*）：

\<WRAP\>

  
^Value^Keyword^

|     |            |
|-----|------------|
| 0   | standard   |
| 1   | landscape  |
| 2   | portrait   |
| 3   | nightscene |

\</WRAP\>\<wrap clear/\>
</td></tr><tr><td>
锐度</td><td>
sharpness</td><td>

接受以下值（可以使用 *值* 或 *关键词*）：

\<WRAP\>

  
^Value^Keyword^

|     |        |
|-----|--------|
| 0   | normal |
| 1   | soft   |
| 2   | hard   |

\</WRAP\>\<wrap clear/\>
</td></tr><tr><td>
快门速度</td><td>
shutterspeed</td><td>

以秒或几分之一秒指定 - 接受十进制或分数。
</td></tr><tr><td>
特殊指令</td><td>
instructions</td><td>
用户自定义字符串。
</td></tr><tr><td>
拍摄距离</td><td>
subjectdistance</td><td>

以米或毫米指定 - 接受十进制或分数。

//<示例://>

**SetAttr META subjectdistance:10.3mm** *   - 10.3 毫米*
**SetAttr META subjectdistance:50m** *   - 50 米*
</td></tr><tr><td>
白平衡</td><td>
whitebalance</td><td>

接受以下值（可以使用 *值* 或 *关键词*）：

\<WRAP\>

  
^Value^Keyword^

|     |        |
|-----|--------|
| 0   | auto   |
| 1   | manual |

\</WRAP\>\<wrap clear/\>
</td></tr><tr><td>

**  
音乐属性**</td><td>
</td><td>

</td></tr><tr><td>
专辑</td><td>
album</td><td>
用户自定义字符串。
</td></tr><tr><td>
专辑歌手</td><td>
albumartist</td><td>
用户自定义字符串。
</td></tr><tr><td>
集合</td><td>
compilation</td><td>

iTunes 集合标签。可以是 **True**（**1**）或 **False**（**0**）。
</td></tr><tr><td>
封套图片</td><td>
coverart</td><td>

这可以设置、添加和删除封套图片。

要设置封套图片（移除所有现有图片），值必须指定为：  
*type***:***\<filename\>*  
要添加封套图片（添加到现有图片）：  
***+**type***:***\<filename\>*  
要移除封套图片（移除特定类型的图片）：  
**-***type*

封套图片类型可以按以下方式指定（可以使用 *值* 或 *关键词*）：  
\<WRAP\>

  
^Value^Keyword^

|     |               |
|-----|---------------|
| 3   | front         |
| 4   | back          |
| 0   | other         |
| 1   | icon          |
| 2   | otherfileicon |
| 5   | leaflet       |
| 6   | media         |
| 7   | leadartist    |
| 8   | artist        |
| 9   | conductor     |
| 10  | band          |
| 11  | composer      |
| 12  | lyricist      |
| 13  | location      |
| 14  | recording     |
| 15  | performance   |
| 16  | vidcap        |
| 17  | colorfulfish  |
| 18  | illustration  |
| 19  | bandlogo      |
| 20  | publisherlogo |

\</WRAP\>\<wrap clear/\>

//<示例://>

**SetAttr META "coverart:3:/mypictures/Pink Floyd.jpg"  
SetAttr META "coverart:front:clip"** *- 从剪贴板设置封面图片*  
**SetAttr META coverart:-back** *   - 移除所有背面封面图片***  
SetAttr META coverart *** - 移除所有图片*
</td></tr><tr><td>
光盘序号</td><td>
discnumber</td><td>

接受单个数字（该光盘的序号），或两个数字，用正斜杠分隔（该光盘的序号和该套件中光盘的总数）。

//<示例://>

**SetAttr META discnumber:3/8**
</td></tr><tr><td>
调性</td><td>
initialkey</td><td>
用户自定义字符串。
</td></tr><tr><td>
最初的歌手</td><td>
origartist</td><td>
用户自定义字符串。
</td></tr><tr><td>
发行日期</td><td>
releasedate</td><td>

接受 **YYYYMMDD** 或 **YYYY-MM-DD** 格式的日期。

//<示例://>

**SetAttr META releasedate:1973-03-01**
</td></tr><tr><td>
音轨序号</td><td>
track</td><td>

接受单个数字（该音轨的序号），或两个数字，用正斜杠分隔（该音轨的序号和该光盘上的音轨总数）。在值后附加 + 来激活自动增量模式。

//<示例://>

**SetAttr META track:5/14**
</td></tr><tr><td>

**  
视频属性**</td><td>
</td><td>

</td></tr><tr><td>
导演</td><td>
directors</td><td>
用户自定义字符串。多个导演可以用分号分隔。
</td></tr><tr><td>
制片人</td><td>
producers</td><td>
用户自定义字符串。多个制片人可以用分号分隔。
</td></tr><tr><td>
编剧</td><td>
writers</td><td>
用户自定义字符串。多个编剧可以用分号分隔。
</td></tr><tr><td>

**  
音乐和视频属性**</td><td>
</td><td>

</td></tr><tr><td>
作者网址</td><td>
authorurl</td><td>
用户自定义字符串。
</td></tr><tr><td>
歌手</td><td>
artist</td><td>
用户自定义字符串。多个歌手可以用分号分隔。
</td></tr><tr><td>
BPM</td><td>
bpm</td><td>
接受数值。
</td></tr><tr><td>
作曲</td><td>
composers</td><td>
用户自定义字符串。多个作曲人可以用分号分隔。
</td></tr><tr><td>
指挥</td><td>
conductor</td><td>
用户自定义字符串。多个指挥可以用分号分隔。
</td></tr><tr><td>
内容组</td><td>
contentgroup</td><td>
用户自定义字符串。
</td></tr><tr><td>
编码</td><td>
encoder</td><td>
用户自定义字符串。
</td></tr><tr><td>
编码软件</td><td>
encodingsoftware</td><td>
用户自定义字符串。
</td></tr><tr><td>
流派</td><td>
genre</td><td>
用户自定义字符串。
</td></tr><tr><td>
情绪</td><td>
mood</td><td>
用户自定义字符串。
</td></tr><tr><td>
出版商</td><td>
publisher</td><td>
用户自定义字符串。
</td></tr><tr><td>
字幕</td><td>
subtitle</td><td>
用户自定义字符串。
</td></tr><tr><td>
年代</td><td>
year</td><td>

接受四位数的年份（**YYYY**）。
</td></tr><tr><td>

**  
文档属性**</td><td>
</td><td>

</td></tr><tr><td>
作者</td><td>
author</td><td>
用户自定义字符串。多个作者可以用分号分隔。
</td></tr><tr><td>
类别</td><td>
category</td><td>
用户自定义字符串。
</td></tr><tr><td>
公司</td><td>
company</td><td>
用户自定义字符串。
</td></tr><tr><td>
内容状态</td><td>
contentstatus</td><td>
用户自定义字符串。
</td></tr><tr><td>
内容类型</td><td>
contenttype</td><td>
用户自定义字符串。
</td></tr><tr><td>
版权</td><td>
copyright</td><td>
用户自定义字符串。
</td></tr><tr><td>
创建者</td><td>
creator</td><td>
用户自定义字符串。
</td></tr><tr><td>
语言</td><td>
language</td><td>
用户自定义字符串。
</td></tr><tr><td>
最后保存者</td><td>
lastsavedby</td><td>
用户自定义字符串。
</td></tr><tr><td>
管理</td><td>
manager</td><td>
用户自定义字符串。
</td></tr><tr><td>
制片人</td><td>
producer</td><td>
用户自定义字符串。
</td></tr><tr><td>
主题</td><td>
subject</td><td>
用户自定义字符串。
</td></tr><tr><td>
标题</td><td>
title</td><td>
用户自定义字符串。
</td></tr></tbody>
</table>