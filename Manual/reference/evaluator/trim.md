\<evalcmd\> Trim && string && Trimmed string. && string && string && String to trim. \</evalcmd\>

Trims leading and trailing spaces from *string* and returns the result.

//<Example://>

    Output( """" + Trim("   Hello   World   ") + """" );
    --> "Hello   World"
