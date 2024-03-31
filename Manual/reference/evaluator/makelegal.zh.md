\<evalcmd\> MakeLegal && string && 已处理的字符串。 && string && string && 输入字符串。 && \[flags\] && string && 可选标志为：

|        |                                                                                                                                                                                       |
|--------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **f** | 正斜杠：将分隔符转换为“/”而不是“\”                                                   |
| **n** | 名称而不是路径：将分隔符替换为“_”(隐含**s**)                                                                                |
| **s** | 子目录模式：将“:”替换为“;”并从 UNC 路径中删除“\\” |

\</evalcmd\>

返回值中 *string* 已删除或替换所有非法路径字符。

//<Example://>

    Output( MakeLegal("*File<?>Name*.txt") )
    --> #File(!)Name#.txt

    Output( MakeLegal("C:\Program Files", "n") )
    --> C;_Program Files

    Output( MakeLegal("\\Server\\Share", "sf") )
    --> Server/Share