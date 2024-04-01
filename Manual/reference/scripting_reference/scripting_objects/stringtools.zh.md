**StringTools** 对象提供了多种用于对字符串进行编码和解码的实用方法。例如，你可以使用 **StringTools** 对象对一段数据进行 Base64 编码，或对 UTF-8 编码的消息头进行解码。

你可以使用 **[DOpusFactory](dopusfactory.zh.md).StringTools** 方法来获取 **StringTools** 对象。

<table>
<thead><tr><th>
方法名</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
Decode</td><td>

\<**[Blob](blob.zh.md)**:source\> 或 \<string:source\>  
\<string:format\></td><td>

*string* 或  
**[Blob](blob.zh.md)**</td><td>

解码经过编码的字符串或数据。

你可以提供 **[Blob](blob.zh.md)** 对象或字符串作为要解码的 *source*。根据 *format* 参数的值，会返回一个字符串或 **[Blob](blob.zh.md)**。有效格式包括：

<table>
<tbody>
<tr class="odd">
<td><strong>base64</strong></td>
<td><em>Base64</em> 将对源进行解码，并返回一个 <strong><a href="blob">Blob</a></strong>。</td>
</tr>
<tr class="even">
<td><strong>quoted</strong></td>
<td><em>Quoted-printable</em> 将对源进行解码，并返回一个 <strong><a href="blob">Blob</a></strong>。</td>
</tr>
<tr class="odd">
<td><strong>utf-8</strong></td>
<td>源将从 UTF-8 转换为本机字符串。</td>
</tr>
<tr class="even">
<td><strong>utf-16</strong><br />
<strong>utf-16-le</strong></td>
<td>源将从 UTF-16 小端序转换为本机字符串。</td>
</tr>
<tr class="odd">
<td><strong>utf-16-be</strong></td>
<td>源将从 UTF-16 大端序转换为本机字符串。</td>
</tr>
<tr class="even">
<td><strong>auto</strong></td>
<td>将调用特殊处理来解码经过 MIME 编码的电子邮件主题（例如以 <strong>=?</strong> 开头的主题），并且如果识别出来，则会返回一个字符串。如果它在开头带有 BOM，它还将检测 UTF-8 或 UTF-16 编码的数据。</td>
</tr>
</tbody>
</table>

如果通过 **"auto"** 或 **"utf-8"** 等进行 UTF-8 或 UTF-16 解码，如果输入数据的开头存在字节顺序标记 (BOM)，则任何字节顺序标记 (BOM) 都将被跳过。

如果未指定 *format*，则默认为 **auto**。否则，*format* 必须设置为上述关键字中的一个或一个有效的代码页名称（例如 **"gb2312"**, **"utf-8"**），或一个 Windows 代码页 ID（例如 **936**, **65001**）。源将使用指定的代码页进行解码，并且会返回一个字符串。
</td></tr><tr><td>
Encode</td><td>

\<**[Blob](blob.zh.md)**:source\> 或 \<string:source\>  
\<string:format\></td><td>

*string* 或  
**[Blob](blob.zh.md)**</td><td>

编码一个字符串或数据。

你可以提供 **[Blob](blob.zh.md)** 对象或字符串作为要解码的 *source*。根据 *format* 参数的值，会返回一个字符串或 **[Blob](blob.zh.md)**。有效格式包括：

<table>
<tbody>
<tr class="odd">
<td><strong>base64</strong></td>
<td><em>Base64</em> 将对源进行编码，并返回一个字符串。</td>
</tr>
<tr class="even">
<td><strong>quoted</strong></td>
<td><em>Quoted-printable</em> 将对源进行编码，并返回一个字符串。</td>
</tr>
<tr class="odd">
<td><strong>utf-8</strong></td>
<td>源将转换为 UTF-8，不带字节顺序标记 (BOM)。</td>
</tr>
<tr class="even">
<td><strong>utf-8 bom</strong></td>
<td>源将转换为 UTF-8，并在开头带有一个 BOM。</td>
</tr>
<tr class="odd">
<td><strong>utf-16</strong><br />
<strong>utf-16-le</strong></td>
<td>源将转换为 UTF-16 小端序，不带 BOM。</td>
</tr>
<tr class="even">
<td><strong>utf-16 bom</strong><br />
<strong>utf-16-le bom</strong></td>
<td>源将转换为 UTF-16 小端序，并带有一个 BOM。</td>
</tr>
<tr class="odd">
<td><strong>utf-16-be</strong></td>
<td>源将转换为 UTF-16 大端序，不带 BOM。</td>
</tr>
<tr class="even">
<td><strong>utf-16-be bom</strong></td>
<td>源将转换为 UTF-16 大端序，并带有一个 BOM。</td>
</tr>
</tbody>
</table>

否则，*format* 必须设置为一个有效的代码页名称（例如 **"gb2312"**, **"utf-8"** 等），或一个 Windows 代码页 ID（例如 **936**, **65001**）。源将使用指定的代码页进行编码，并且会返回一个 **[Blob](blob.zh.md)**。
</td></tr><tr><td>
IsASCII</td><td>

\<string:input\></td><td>

*bool*</td><td>

测试输入字符串以了解它是否只包含可以在 ASCII 中表示的字符。

如果结果为 false，则字符串不适合保存到文本文件中，除非你使用 Unicode 格式（例如 UTF-8）。

此检查不受区域设置或代码页的影响。相反，它测试字符串是否仅由 7 位 ASCII 字符组成，以便在将字符串保存到文本文件中然后在任何其它计算机上加载它时，不会丢失或修改任何字符。
</td></tr><tr><td>
LanguageStr</td><td>

\<string:name\> 或  
\<int:id\></td><td>

*string*</td><td>

返回当前选定语言中的一个翻译字符串。主要用于内部使用。

当前定义的字符串如下：

| ID            | 英文字符串 |
|---------------|-------------------------|
| FavoritesBar  | Favorites Bar           |
| FindResults   | Find Results            |
| CopySelection | Copy Selection          |
| CopyAll       | Copy All                |
</td></tr><tr><td>
MakeLegal</td><td>

\<string:name\> \[\<string:flags\>\]</td><td>

*string*</td><td>

从提供的字符串中删除任何不合法文件名字符。

可选标志包括：

|       |                                                                                                                                                                                       |
|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **f** | 正斜杠：将分隔符转换为 `/` 而不是 `\`                                                   |
| **n** | 名称而不是路径：用 `_` 替换分隔符（隐含 **s**）                                                                                |
| **s** | 子目录模式：用 `;` 替换 `:` 并从 UNC 路径中删除 `\\` |
</td></tr><tr><td>
RemoveDiacritics</td><td>

\<string:input\></td><td>

*string*</td><td>

返回一个 input 字符串副本，其中已删除任何变音符号（重音符号）。例如，“á”将转换为“a”。

此函数使用与整个 Opus 的模式匹配的“忽略变音符号”选项相同的规则。
</td></tr><tr><td>
Truncate</td><td>

\<string:input\> 或 *object*:[Path](path.zh.md) \<int:length\> \[\<int:type\>\]</td><td>

*string*</td><td>

将指定的输入字符串截断到请求的字符数。

可选 *type* 参数指定截断类型。有效值包括：

|     |                        |
|-----|------------------------|
| 0   | 在右侧截断  |
| 1   | 在左侧截断   |
| 2   | 在中间截断 |

如果未指定，则当 *input* 为 [Path](path.zh.md) 对象时，默认为 **2**；否则，默认为 **0**。
如果输入值是 [Path](path.zh.md) 并且选择了中间截断，该函数会正确考虑路径分隔符。