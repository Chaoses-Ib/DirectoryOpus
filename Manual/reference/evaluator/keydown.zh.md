\<evalcmd\> KeyDown && bool && 指定的按键按下为 **True**。 && key && 测试的修饰键。 && \[key...\] && 第二个修饰键... \</evalcmd\>

如果指定的修饰键 *key* 或 *keys* 被按下，则返回**True**。如果提供了多个键，则所有键都必须被按下才会返回**true**。

有效的关键字是 **none**、**shift**、**ctrl** 和 **alt**。

//<Example://>

    if (KeyDown("shift", "ctrl"")) { ... } // shift 和 ctrl 都被按下？