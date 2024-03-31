当从 [函数](/Manual/evaluator/applicable_contexts/functions/commands.zh.md)中调用时，中止函数中剩余代码的执行。

//<Example://>

    =if ("%USERNAME%" == "jon") AbortFunc();
    @confirm HI，非 Jon 的用户！