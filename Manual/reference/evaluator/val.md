\<evalcmd\> Val && var && Value of the named argument. && varname && string && Name of the argument. \</evalcmd\>

Returns the value of a variable; *varname* is provided as a quoted string. This is useful for variables which contain characters that would confuse the Evaluator's parser (e.g. those containing punctuation symbols).

//<Example://>

    flag = Val("$glob:flag"); // get value of the global variable "flag"
