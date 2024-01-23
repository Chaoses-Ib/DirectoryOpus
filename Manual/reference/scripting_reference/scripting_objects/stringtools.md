# StringTools

A **StringTools** object provides several utility methods for encoding and decoding strings. For example, you can use a **StringTools** object to Base64-encode a chunk of data, or decode a UTF-8 encoded message header.

You can obtain a **StringTools** object using the **[DOpusFactory](dopusfactory.md).StringTools** method.

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Decode | \<**[Blob](blob.md)**:source\> or \<string:source\>  <br />\<string:format\> | *string* or  <br />**[Blob](blob.md)** | Decodes an encoded string or data.<br /><br />You can provide either a **[Blob](blob.md)** object or a string as the *source* to decode. Depending on the value of the *format* argument, either a string or a **[Blob](blob.md)** is returned. Valid formats are:<br /><br /><table><br /><tbody><br /><tr class="odd"><br /><td><strong>base64</strong></td><br /><td>The source will be <em>Base64</em>-decoded, and a <strong><a href="blob">Blob</a></strong> is returned.</td><br /></tr><br /><tr class="even"><br /><td><strong>quoted</strong></td><br /><td>The source will be <em>Quoted-printable</em>-decoded, and a <strong><a href="blob">Blob</a></strong> is returned.</td><br /></tr><br /><tr class="odd"><br /><td><strong>utf-8</strong></td><br /><td>The source will be converted from UTF-8 to a native string.</td><br /></tr><br /><tr class="even"><br /><td><strong>utf-16</strong><br /><br /><strong>utf-16-le</strong></td><br /><td>The source will be converted from UTF-16 Little Endian to a native string.</td><br /></tr><br /><tr class="odd"><br /><td><strong>utf-16-be</strong></td><br /><td>The source will be converted from UTF-16 Big Endian to a native string.</td><br /></tr><br /><tr class="even"><br /><td><strong>auto</strong></td><br /><td>Special handling is invoked to decode a MIME-encoded email subject (e.g. one beginning with <strong>=?</strong>), and a string is returned if identified. It will also detect UTF-8 or UTF-16 encoded data if it has a BOM at the beginning.</td><br /></tr><br /></tbody><br /></table><br /><br />If decoding UTF-8 or UTF-16 (via **"auto"** or **"utf-8"**, etc.), any byte-order-mark (BOM) will be skipped if one exists at the beginning of the input data.<br /><br />If *format* is not specified the default is **auto**. Otherwise, *format* must be set to one of the above keywords or a valid code-page name (e.g. **"gb2312"**, **"utf-8"**), or a Windows code-page ID (e.g. **936**, **65001**). The source will be decoded using the specified code-page and a string is returned. |
| Encode | \<**[Blob](blob.md)**:source\> or \<string:source\>  <br />\<string:format\> | *string* or  <br />**[Blob](blob.md)** | Encodes a string or data.<br /><br />You can provide either a **[Blob](blob.md)** object or a string as the *source* to decode. Depending on the value of the *format* argument, either a string or a **[Blob](blob.md)** is returned. Valid formats are:<br /><br /><table><br /><tbody><br /><tr class="odd"><br /><td><strong>base64</strong></td><br /><td>The source will be <em>Base64</em>-encoded, and a string is returned.</td><br /></tr><br /><tr class="even"><br /><td><strong>quoted</strong></td><br /><td>The source will be <em>Quoted-printable</em>-encoded, and a string is returned.</td><br /></tr><br /><tr class="odd"><br /><td><strong>utf-8</strong></td><br /><td>The source will be converted to UTF-8 without a byte-order-mark (BOM).</td><br /></tr><br /><tr class="even"><br /><td><strong>utf-8 bom</strong></td><br /><td>The source will be converted to UTF-8 with a BOM at the start.</td><br /></tr><br /><tr class="odd"><br /><td><strong>utf-16</strong><br /><br /><strong>utf-16-le</strong></td><br /><td>The source will be converted to UTF-16 Little Endian without a BOM.</td><br /></tr><br /><tr class="even"><br /><td><strong>utf-16 bom</strong><br /><br /><strong>utf-16-le bom</strong></td><br /><td>The source will be converted to UTF-16 Little Endian with a BOM.</td><br /></tr><br /><tr class="odd"><br /><td><strong>utf-16-be</strong></td><br /><td>The source will be converted to UTF-16 Big Endian without a BOM.</td><br /></tr><br /><tr class="even"><br /><td><strong>utf-16-be bom</strong></td><br /><td>The source will be converted to UTF-16 Big Endian with a BOM.</td><br /></tr><br /></tbody><br /></table><br /><br />Otherwise, *format* must be set to a valid code-page name (e.g. **"gb2312"**, **"utf-8"** etc.), or a Windows code-page ID (e.g. **936**, **65001**). The source will be encoded using the specified code-page and a **[Blob](blob.md)** is returned. |
| IsASCII | \<string:input\> | *bool* | Tests the input string to see if it only contains characters that can be represented in ASCII.<br /><br />If the result is false, the string is not safe to save into a text file unless you use a Unicode format such as UTF-8.<br /><br />This check is not affected by locales or codepages. Instead, it tests whether the string consists of only 7-bit ASCII characters, such that no characters will be lost or modified if you save the string to a text file and then load it back on any other computer. |
| RemoveDiacritics | \<string:input\> | *string* | Returns a copy of the input string with any diacritics (accent symbols) removed. For example, "á" would be converted to "a".<br /><br />This function uses the same rules that are used by the "ignore diacritics" options for pattern matching throughout Opus. |
