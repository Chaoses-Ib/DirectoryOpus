\<evalcmd\> AbortFunc && none \</evalcmd\>

When called from within a [function](/Manual/evaluator/applicable_contexts/functions/commands.md), aborts the execution of the remainder of the function.

//<Example://>

    =if ("%USERNAME%" == "jon") AbortFunc();
    @confirm Hi there, person who isn't Jon!
