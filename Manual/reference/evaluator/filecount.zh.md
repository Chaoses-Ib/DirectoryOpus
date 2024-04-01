\<evalcmd\>  FileCount && int && 与指定条件匹配的项数。 && selected && bool && **True** 表示已选定项，**False** 表示所有项。 && pattern && string && 文件名通配符模式。使用 **dirs:** 前缀仅匹配目录或使用 **files:** 前缀仅匹配文件。 && \[pattern...\] && string && 其它文件名模式... \</evalcmd\>

返回与 *pattern* 匹配的项总数。仅针对所选项目计数时，为 *selected* 参数指定 **true**。

指定多个模式时，返回值是所有与已提供模式匹配项的总和。

//<Example://>

    if (FileCount("*.jpg") > 2) { ... } // 文件夹中有至少三个 jpg 
    if (FileCount(true, "dirs:new*") == 5) { ... } // 已选择以 new 起头的 5 个文件夹

*另请参阅:* [isselected](isselected.zh.md)