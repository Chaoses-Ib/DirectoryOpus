\<evalcmd\> Select && var && Value at the specified index. && index && int && Index of value to return. && value1 && var && First value (index 0) && \[value2...\] && var && Second value (index 1)... \</evalcmd\>

Returns the value identified by the specified *index*. The index of the first item is 0.

This performs an array-like function (the evaluator does not currently support arrays).

//<Example://>

    day = 3;
    Output(Select(day, "Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"));
    --> Thu
