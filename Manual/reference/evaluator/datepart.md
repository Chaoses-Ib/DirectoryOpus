\<evalcmd\> DatePart && string && Requested part of the specified date. && date && date && Date you want a part of. && part && string && Part you want. Date parts are:

|      |                                           |
|------|-------------------------------------------|
| d    | Day of month, no leading zero             |
| dd   | Day of month, leading zero                |
| D    | Day of week (1 = Sunday)                  |
| DD   | Day of week as a number (1 = Monday)      |
| ddd  | Day of week short name (e.g. Wed)         |
| dddd | Day of week long name (e.g. Wednesday)    |
| w    | ISO week, no leading zero                 |
| ww   | ISO week, leading zero                    |
| W    | Simple week, no leading zero              |
| WW   | Simple week, leading zero                 |
| M    | Month, no leading zero                    |
| MM   | Month, leading zero                       |
| MMM  | Month short name (e.g. Jan)               |
| MMMM | Month long name (e.g. January)            |
| y    | Year last two digits, no leading zero     |
| yy   | Year last two digits, leading zero        |
| yyyy | Year                                      |
| Y    | ISO year last two digits, no leading zero |
| YY   | ISO year last two digits, leading zero    |
| YYYY | ISO year                                  |
| gg   | Period/era string                         |

Time parts are:

|     |                                       |
|-----|---------------------------------------|
| h   | Hours, no leading zero, 12 hour clock |
| hh  | Hours, leading zero, 12 hour clock    |
| H   | Hours, no leading zero, 24 hour clock |
| HH  | Hours, leading zero, 24 hour clock    |
| m   | Minutes, no leading zero              |
| mm  | Minutes, leading zero                 |
| s   | Seconds, no leading zero              |
| ss  | Seconds, leading zero                 |
| t   | One-character AM/PM (e.g. A or P)     |
| tt  | Multiple-character AM/PM%0            |

\</evalcmd\>

Returns the value of the specified part.

//<Example://>

    Output(DatePart("2006-01-01", "yy"))
    --> 06
