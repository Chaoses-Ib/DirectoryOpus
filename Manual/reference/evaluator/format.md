\<evalcmd\> Format && string && Formatted string. && fmtstring && string && String containing insertion codes. Codes are **%1** for the first argument, **%2** for the second argument, and so on.

To include a literal percent character in the output string, use the special code **%%**.&& arg1 && any && The argument to insert for code **%1**. && \[arg2...\] && any && The argument to insert for code **%2** etc... \</evalcmd\>

Returns the formatted output string.

//<Example://>

    Output(Format("Hello %1!", "Jon"))
    --> Hello Jon!

*See also:* [as](as.md)
