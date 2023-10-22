\<evalcmd\> Elapsed && double or bool && Elapsed time in milliseconds, or true or false. && name && string && Name of the elapse timer. && \[time\] && double && Time in milliseconds to test for. && \[reset\] && bool && True if timer should be reset. \</evalcmd\>

Measures the time in milliseconds of a named *elapse timer* since it was started. Timers are global, so you should pick a unique name.

The first time the specified timer is measured it is started.

If called with just a single argument, the return value is the number of milliseconds since the timer was started.

If the optional *time* argument is given, the \`Elapsed()\` function tests whether the specified number of milliseconds has elapsed, and the function returns either **true** or **false**. Note that in this mode, the function also returns **true** when the timer is started for the first time.

If the *reset* argument is set to **true**, the timer will be reset to zero if the specified time has elapsed.

//<Example://>

    if (Elapsed("test_timer", 5000, true)) { ... }
