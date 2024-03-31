返回一个字符串，指出传入变量的类型。

类型有：**bool**，**int**，**uint**，**int64**，**uint64**，**double**，**date**，**str**，**path** 和 **map**。

请参阅 [求值器变量](/Manual/evaluator/variable_types.zh.md) 页面了解有关不同类型的详细信息。

//<Example://>

    a = -5;
    Output( TypeOf(a) );
    --> int

*另请参阅：* [as](as.zh.md)