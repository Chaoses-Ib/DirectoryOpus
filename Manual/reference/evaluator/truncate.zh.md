\<evalcmd\> Truncate &amp;&amp; string &amp;&amp; 截断后的字符串。 &amp;&amp; string &amp;&amp; string &amp;&amp; 要截断的输入字符串。 &amp;&amp; length &amp;&amp; int &amp;&amp; 要截断到的字符数。 &amp;&amp; \[type\] &amp;&amp; int &amp;&amp; 截断类型。选项为：

|     |                        |
|-----|------------------------|
| 0   | 从右向左截断  |
| 1   | 从左向右截断   |
| 2   | 从中间截断 |

\</evalcmd\>

将字符串截断到指定字符数。

如果未指定截断类型，则在输入值为“路径”时，默认值为“2”，否则，默认值为“0”。

如果输入值是“路径”，并且选择了中间截断，则该函数将正确地考虑路径分隔符。

//<Example://>

    Output( Truncate("C:\Program Files\GPSoftware\Directory Opus\dopus.exe" as path, 32, 2) );
    --> C:\Program Files\GP...\dopus.exe