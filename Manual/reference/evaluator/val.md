\<evalcmd\> Val && var && Value of the named argument. && varname && string && Name of the argument. \</evalcmd\>

Returns the value of a variable; *varname* is provided as a quoted string. This is useful for variables which contain characters that would confuse the Evaluator's parser (e.g. if the name begins with a number).

//<Example://>

    flag = Val("35mmfocallength"); // get value of the 35mmfocallength field
