\<evalcmd\> IsParent && int && 两个路径差别多少层。 && parent && path && 要测试的父路径。 && child && path && 要用于对比父路径的子路径。 \</evalcmd\>

测试 *parent* 是否为 *child* 的父路径。

如果否，则返回 `0`。否则，返回 *parent* 比 *child* 高的层数。

//<Example://>

    parentPath = "C:\Windows"
    childPath = "C:\Windows\System32"
    Output( IsParent(parentPath, childPath) )
    --> 1

*另请参阅：*  
[count](count.zh.md)  
[parent](parent.zh.md)