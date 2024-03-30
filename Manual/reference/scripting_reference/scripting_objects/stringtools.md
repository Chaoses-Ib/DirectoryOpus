# StringTools

A **StringTools** object provides several utility methods for encoding and decoding strings. For example, you can use a **StringTools** object to Base64-encode a chunk of data, or decode a UTF-8 encoded message header.

You can obtain a **StringTools** object using the **[DOpusFactory](dopusfactory.md).StringTools** method.

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Decode</td><td>

\<**[Blob](blob.md)**:source\> or \<string:source\>  
\<string:format\></td><td>

*string* or  
**[Blob](blob.md)**</td><td>

Decodes an encoded string or data.

You can provide either a **[Blob](blob.md)** object or a string as the *source* to decode. Depending on the value of the *format* argument, either a string or a **[Blob](blob.md)** is returned. Valid formats are:

<table>
<tbody>
<tr class="odd">
<td><strong>base64</strong></td>
<td>The source will be <em>Base64</em>-decoded, and a <strong><a href="blob">Blob</a></strong> is returned.</td>
</tr>
<tr class="even">
<td><strong>quoted</strong></td>
<td>The source will be <em>Quoted-printable</em>-decoded, and a <strong><a href="blob">Blob</a></strong> is returned.</td>
</tr>
<tr class="odd">
<td><strong>utf-8</strong></td>
<td>The source will be converted from UTF-8 to a native string.</td>
</tr>
<tr class="even">
<td><strong>utf-16</strong><br />
<strong>utf-16-le</strong></td>
<td>The source will be converted from UTF-16 Little Endian to a native string.</td>
</tr>
<tr class="odd">
<td><strong>utf-16-be</strong></td>
<td>The source will be converted from UTF-16 Big Endian to a native string.</td>
</tr>
<tr class="even">
<td><strong>auto</strong></td>
<td>Special handling is invoked to decode a MIME-encoded email subject (e.g. one beginning with <strong>=?</strong>), and a string is returned if identified. It will also detect UTF-8 or UTF-16 encoded data if it has a BOM at the beginning.</td>
</tr>
</tbody>
</table>

If decoding UTF-8 or UTF-16 (via **"auto"** or **"utf-8"**, etc.), any byte-order-mark (BOM) will be skipped if one exists at the beginning of the input data.

If *format* is not specified the default is **auto**. Otherwise, *format* must be set to one of the above keywords or a valid code-page name (e.g. **"gb2312"**, **"utf-8"**), or a Windows code-page ID (e.g. **936**, **65001**). The source will be decoded using the specified code-page and a string is returned.
</td></tr><tr><td>
Encode</td><td>

\<**[Blob](blob.md)**:source\> or \<string:source\>  
\<string:format\></td><td>

*string* or  
**[Blob](blob.md)**</td><td>

Encodes a string or data.

You can provide either a **[Blob](blob.md)** object or a string as the *source* to decode. Depending on the value of the *format* argument, either a string or a **[Blob](blob.md)** is returned. Valid formats are:

<table>
<tbody>
<tr class="odd">
<td><strong>base64</strong></td>
<td>The source will be <em>Base64</em>-encoded, and a string is returned.</td>
</tr>
<tr class="even">
<td><strong>quoted</strong></td>
<td>The source will be <em>Quoted-printable</em>-encoded, and a string is returned.</td>
</tr>
<tr class="odd">
<td><strong>utf-8</strong></td>
<td>The source will be converted to UTF-8 without a byte-order-mark (BOM).</td>
</tr>
<tr class="even">
<td><strong>utf-8 bom</strong></td>
<td>The source will be converted to UTF-8 with a BOM at the start.</td>
</tr>
<tr class="odd">
<td><strong>utf-16</strong><br />
<strong>utf-16-le</strong></td>
<td>The source will be converted to UTF-16 Little Endian without a BOM.</td>
</tr>
<tr class="even">
<td><strong>utf-16 bom</strong><br />
<strong>utf-16-le bom</strong></td>
<td>The source will be converted to UTF-16 Little Endian with a BOM.</td>
</tr>
<tr class="odd">
<td><strong>utf-16-be</strong></td>
<td>The source will be converted to UTF-16 Big Endian without a BOM.</td>
</tr>
<tr class="even">
<td><strong>utf-16-be bom</strong></td>
<td>The source will be converted to UTF-16 Big Endian with a BOM.</td>
</tr>
</tbody>
</table>

Otherwise, *format* must be set to a valid code-page name (e.g. **"gb2312"**, **"utf-8"** etc.), or a Windows code-page ID (e.g. **936**, **65001**). The source will be encoded using the specified code-page and a **[Blob](blob.md)** is returned.
</td></tr><tr><td>
IsASCII</td><td>
\<string:input\></td><td>

*bool*</td><td>
Tests the input string to see if it only contains characters that can be represented in ASCII.

If the result is false, the string is not safe to save into a text file unless you use a Unicode format such as UTF-8.

This check is not affected by locales or codepages. Instead, it tests whether the string consists of only 7-bit ASCII characters, such that no characters will be lost or modified if you save the string to a text file and then load it back on any other computer.
</td></tr><tr><td>
LanguageStr</td><td>
\<string:name\> or  
\<int:id\></td><td>

*string*</td><td>

Returns a translated string in the currently selected language. Mainly needed for internal use.

The currently defined strings are:

| ID            | English language string |
|---------------|-------------------------|
| FavoritesBar  | Favorites Bar           |
| FindResults   | Find Results            |
| CopySelection | Copy Selection          |
| CopyAll       | Copy All                |
</td></tr><tr><td>
MakeLegal</td><td>

\<string:name\> \[\<string:flags\>\]</td><td>

*string*</td><td>

Strips any illegal filename characters from the supplied string.

The optional flags are:

|       |                                                                                                                                                                                       |
|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **f** | forward slashes: convert separators to `/` instead of `\`                                                   |
| **n** | name instead of path: replace separators with `_` (implies **s**)                                                                                |
| **s** | subdirectory mode: replace `:` with `;` and remove `\\` from UNC paths |
</td></tr><tr><td>
RemoveDiacritics</td><td>
\<string:input\></td><td>

*string*</td><td>
Returns a copy of the input string with any diacritics (accent symbols) removed. For example, "á" would be converted to "a".

This function uses the same rules that are used by the "ignore diacritics" options for pattern matching throughout Opus.
</td></tr><tr><td>
Truncate</td><td>

\<string:input\> or *object*:[Path](path.md) \<int:length\> \[\<int:type\>\]</td><td>

*string*</td><td>

Truncates the specified input string to the requested number of characters.

The optional *type* argument specifies the truncation type. Valid values are:

|     |                        |
|-----|------------------------|
| 0   | truncate on the right  |
| 1   | truncate on the left   |
| 2   | truncate in the middle |

If not specified, the default is **2** if *input* is a [Path](path.md) object, otherwise the default is **0**.

If the input value is a [Path](path.md) and middle truncation is selected, the function takes path separators into account correctly.
</td></tr></tbody>
</table>

