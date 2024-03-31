\<evalcmd\> URLEncode && 字符串 && **字符串** 的编码/解码版本。 && 字符串 && 字符串 && 要编码或解码的输入字符串。 && \[flags\] && 字符串 && 可选标志有：

|       |                                                                           |
|-------|---------------------------------------------------------------------------|
| **d** | 解码：解码字符串而不是编码                                  |
| **g** | google：针对 Google 的编码（空格转换为 **+** 符号） |
| **r** | rfc：符合 RFC 的编码（**~.-\_** 字符不编码）     |

\</evalcmd\>

使用 URL 编码对字符串进行编码或解码。

//<Example://>

    Output( URLEncode("File Name") );
    --> File%20Name

    Output( URLEncode("File Name", "g") );
    -> File+Name

    Output( URLEncode("File%20Name", "d") );
    -> File Name