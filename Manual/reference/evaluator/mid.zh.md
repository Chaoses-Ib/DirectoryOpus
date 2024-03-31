\<evalcmd\> Mid && string && 指定部分字符串。 && string && string && 要返回指定部分的输入字符串。 && start && int && 开始返回的位置（0 为最左边的位置）。 && \[length\] && int && 返回字符串的长度。 \</evalcmd\>

从位置 *start* 开始，从 *string* 返回 *length* 个字符。如果 *length* 为 -1 或省略，则从 *start* 返回到字符串的末尾。

//<范例://>

    Output( Mid("Hello To You", 6, 2) );
    --> To

*另请参见：*  
[left](left.zh.md)  
[right](right.zh.md)