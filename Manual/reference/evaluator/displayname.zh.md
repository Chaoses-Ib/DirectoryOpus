\<evalcmd\> DisplayName && string && 文件或文件夹的显示名称。 && path && path && 查询显示名称的路径。 && \[flags\] && string && 可选标志为：

|       |                                               |
|-------|-----------------------------------------------|
| **f** | 返回文件部分（最终组件）            |
| **p** | 返回解析路径                           |
| **r** | 解析到实际位置（例如库文件） |

\</evalcmd\>

返回文件或文件夹的显示名称。

//<Example://>

    Output(DisplayName("/desktop"));
    --> 桌面

    Output(DisplayName("/desktop", "p"));
    --> C:\Users\jon\Desktop

*另请参阅:* [resolve](resolve.zh.md)