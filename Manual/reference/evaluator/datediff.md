\<evalcmd\> DateDiff && int && Difference between the two dates. && units && string && Unit type to return. Valid unit types are:

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

&& date1 && date && The first date. && date2 && date && The second date. \</evalcmd\>

Returns the difference between the two supplied dates, expressed as *units*.

//<Example://>

    Output(DateDiff("yyyy", "2021-01-01", "2023-01-01"))
    --> 2
