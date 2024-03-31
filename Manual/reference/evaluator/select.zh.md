\<evalcmd\> 选择 && var && 值处于指定的索引处。 && index && int && 要返回的值的索引。 && value1 && var && 第一个值（索引 0） && \[value2...\] && var && 第二个值（索引 1）... \</evalcmd\>

返回由指定 *index* 标识的值。第一个项目的索引为 0。

此操作执行类似数组的功能（目前，求值器不支持数组）。

//<Example://>

    day = 3;
    Output(Select(day, "Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"));
    --> Thu