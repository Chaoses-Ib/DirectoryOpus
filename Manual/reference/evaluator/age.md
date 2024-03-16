\<evalcmd\> Age && int && Difference between the current date and the supplied date. && date && date && The date in question. && \[units\] && string && Unit type to return (defaults to "d" for days). Valid unit types are:

|      |                                    |
|------|------------------------------------|
| yyyy | Years                              |
| q    | Quarter years                      |
| m    | Months                             |
| y    | Days                               |
| d    | Days                               |
| w    | Whole weeks                        |
| ww   | Calendar weeks (number of Sundays) |
| h    | Hours                              |
| n    | Minutes                            |
| s    | Seconds                            |

\</evalcmd\>

(Opus 13.3.4 and above)

Returns the difference between the the current date and the supplied dates, expressed as *units* (defaults to days).

//<Example://>

    Output(Age("2021-01-01"))
    --> 1158
