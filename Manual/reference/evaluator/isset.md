\<evalcmd\> IsSet && bool && **True** if all specified variables exist. && name && var && Name of variable to test for. && \[name...\] && var && Additional variable names... \</evalcmd\>

Returns **True** if all specified variables exist (within the context of this evaluation). Returns **False** if any do not exist.

//<Example://>

    if (IsSet("j")) { ... } // does a variable called "j" exist?
    if (IsSet("name", "ext")) { ... } // do variables called "name" and "ext" both exist?

*See also:* [val](val.md)
