\<evalcmd\> TypeOf && string && Type of the supplied variable. && variable && var && Any variable. \</evalcmd\>

Returns a string indicating the type of the passed-in variable.

Types are: **bool**, **int**, **uint**, **int64**, **uint64**, **double**, **date**, **str**, **path** and **map**.

See the page on [evaluator variables](/Manual/evaluator/variable_types.md) for information about the different types.

//<Example://>

    a = -5;
    Output( TypeOf(a) );
    --> int

*See also:* [as](as.md)
