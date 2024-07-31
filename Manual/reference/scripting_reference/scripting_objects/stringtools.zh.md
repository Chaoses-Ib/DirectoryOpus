# StringTools

一个 **StringTools** 对象提供了用于编码和解码字符串的若干实用方法。例如，你可以使用一个 **StringTools** 对象对一段数据进行 Base64 编码，或解码一个 UTF-8 编码的消息头。

你可以使用 **[DOpusFactory](dopusfactory.zh.md).StringTools** 方法获得一个 **StringTools** 对象。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Decode</td><td>

\<**[Blob](blob.zh.md)**:source\> 或 \<string:source\>  
\<string:format\></td><td>

*string* 或  
**[Blob](blob.zh.md)**</td><td>

解码一个编码的字符串或数据。

你可以提供一个 **[Blob](blob.zh.md)** 对象或一个字符串作为要解码的 *source*。根据 *format* 参数的值，将返回一个字符串或一个 **[Blob](blob.zh.md)**。有效的格式为：

<table>
<tbody>
<tr class="odd">
<td><strong>base64</strong></td>
<td>source 将被 <em>Base64</em> 解码，并返回一个 <strong><a href="blob">Blob</a></strong>。</td>
</tr>
<tr class="even">
<td><strong>quoted</strong></td>
<td>source 将被 <em>Quoted-printable</em> 解码，并返回一个 <strong><a href="blob">Blob</a></strong>。</td>
</tr>
<tr class="odd">
<td><strong>utf-8</strong></td>
<td>source 将被从 UTF-8 转换为本地字符串。</td>
</tr>
<tr class="even">
<td><strong>utf-16</strong><br />
<strong>utf-16-le</strong></td>
<td>source 将被从 UTF-16 小端转换为本地字符串。</td>
</tr>
<tr class="odd">
<td><strong>utf-16-be</strong></td>
<td>source 将被从 UTF-16 大端转换为本地字符串。</td>
</tr>
<tr class="even">
<td><strong>auto</strong></td>
<td>将调用特殊处理以解码 MIME 编码的电子邮件主题（例如，以 <strong>=?</strong> 开头的主题），如果识别出来，则返回一个字符串。如果数据开头有 BOM，它也会检测 UTF-8 或 UTF-16 编码的数据。</td>
</tr>
</tbody>
</table>

如果解码 UTF-8 或 UTF-16（通过 **"auto"** 或 **"utf-8"** 等），如果输入数据开头存在字节顺序标记 (BOM)，则会跳过它。

如果未指定 *format*，则默认值为 **auto**。否则，*format* 必须设置为上述关键字之一或有效的代码页名称（例如 **"gb2312"**、**"utf-8"**），或 Windows 代码页 ID（例如 **936**、**65001**）。source 将使用指定的代码页进行解码，并返回一个字符串。
</td></tr><tr><td>
Encode</td><td>

\<**[Blob](blob.zh.md)**:source\> 或 \<string:source\>  
\<string:format\></td><td>

*string* 或  
**[Blob](blob.zh.md)**</td><td>

编码字符串或数据。

你可以提供一个 **[Blob](blob.zh.md)** 对象或一个字符串作为要解码的 *source*。根据 *format* 参数的值，将返回一个字符串或一个 **[Blob](blob.zh.md)**。有效的格式为：

<table>
<tbody>
<tr class="odd">
<td><strong>base64</strong></td>
<td>source 将被 <em>Base64</em> 编码，并返回一个字符串。</td>
</tr>
<tr class="even">
<td><strong>quoted</strong></td>
<td>source 将被 <em>Quoted-printable</em> 编码，并返回一个字符串。</td>
</tr>
<tr class="odd">
<td><strong>utf-8</strong></td>
<td>source 将被转换为不带字节顺序标记 (BOM) 的 UTF-8。</td>
</tr>
<tr class="even">
<td><strong>utf-8 bom</strong></td>
<td>source 将被转换为开头带 BOM 的 UTF-8。</td>
</tr>
<tr class="odd">
<td><strong>utf-16</strong><br />
<strong>utf-16-le</strong></td>
<td>source 将被转换为不带 BOM 的 UTF-16 小端。</td>
</tr>
<tr class="even">
<td><strong>utf-16 bom</strong><br />
<strong>utf-16-le bom</strong></td>
<td>source 将被转换为开头带 BOM 的 UTF-16 小端。</td>
</tr>
<tr class="odd">
<td><strong>utf-16-be</strong></td>
<td>source 将被转换为不带 BOM 的 UTF-16 大端。</td>
</tr>
<tr class="even">
<td><strong>utf-16-be bom</strong></td>
<td>source 将被转换为开头带 BOM 的 UTF-16 大端。</td>
</tr>
</tbody>
</table>

否则，*format* 必须设置为有效的代码页名称（例如 **"gb2312"**、**"utf-8"** 等），或 Windows 代码页 ID（例如 **936**、**65001**）。source 将使用指定的代码页进行编码，并返回一个 **[Blob](blob.zh.md)**。
</td></tr><tr><td>
IsASCII</td><td>

\<string:input\></td><td>

*bool*</td><td>

测试输入字符串，查看它是否只包含可以在 ASCII 中表示的字符。

如果结果为 false，则该字符串不适合保存到文本文件，除非你使用 UTF-8 等 Unicode 格式。

此检查不受区域设置或代码页的影响。相反，它测试字符串是否仅包含 7 位 ASCII 字符，这样即使你将字符串保存到文本文件，然后在任何其它计算机上加载它，也不会丢失或修改任何字符。
</td></tr><tr><td>
LanguageStr</td><td>

\<string:name\> 或  
\<int:id\></td><td>

*string*</td><td>

返回当前选定语言的翻译后的字符串。主要用于内部使用。

当前定义的字符串为：

| ID            | 英语语言字符串 |
|---------------|-------------------------|
| FavoritesBar  | Favorites Bar           |
| FindResults   | Find Results            |
| CopySelection | Copy Selection          |
| CopyAll       | Copy All                |
</td></tr><tr><td>
MakeLegal</td><td>

\<string:name\> \[\<string:flags\>\]</td><td>

*string*</td><td>

从提供的字符串中剥离任何非法文件名字符。

可选标志为：

|       |                                                                                                                                                                                       |
|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **f** | 正斜杠：将分隔符转换为 `/` 而不是 `\`                                                   |
| **n** | 名称而不是路径：将分隔符替换为 `_`（意味着 **s**）                                                                                |
| **s** | 子目录模式：将 `:` 替换为 `;` 并从 UNC 路径中删除 `\\` |
</td></tr><tr><td>
RemoveDiacritics</td><td>

\<string:input\></td><td>

*string*</td><td>

返回输入字符串的副本，其中删除了所有变音符号（重音符号）。例如，"á" 将被转换为 "a"。

此函数使用与 Opus 中用于模式匹配的“忽略变音符号”选项相同的规则。
</td></tr><tr><td>
Truncate</td><td>

\<string:input\> 或 *object*:[Path](path.zh.md) \<int:length\> \[\<int:type\>\]</td><td>

*string*</td><td>

将指定的输入字符串截断为请求的字符数。

可选的 *type* 参数指定截断类型。有效值为：

|     |                        |
|-----|------------------------|
| 0   | 右侧截断              |
| 1   | 左侧截断              |
| 2   | 中间截断              |

如果未指定，则默认值为 **2**（如果 *input* 是 [Path](path.zh.md) 对象），否则默认值为 **0**。

如果输入值为 [Path](path.zh.md) 并且选择了中间截断，则该函数将正确考虑路径分隔符。
</td></tr></tbody>
</table>