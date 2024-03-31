\<evalcmd\> IsPath && 布尔值 && 如果 *path* 为完全限定路径名，则为 **True**。 && path && path && 要测试的路径。 \</evalcmd\>

如果 *path* 是完全限定的路径名，则返回 **True**，否则返回 **False**。

//<示例://>

    Output(IsPath("C:\Windows\System32"))
    --> true

    Output(IsPath("System32"))
    --> false