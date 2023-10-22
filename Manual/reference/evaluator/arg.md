\<evalcmd\> Arg && string && Value of the named argument. && argname && string && Name of the user command argument. \</evalcmd\>

Returns the value of a [user command](/Manual/customize/the_customize_dialog/user_commands.md) argument. User commands can therefore use the Evaluator to modify their behavior based on the value of a supplied argument.

//<Example://>

    @if:=(Arg("NAME")=="jon")
    echo Hi Jon!
    @if:else
    echo Who are you?
