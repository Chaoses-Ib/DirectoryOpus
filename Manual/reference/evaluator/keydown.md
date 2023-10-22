\<evalcmd\> KeyDown && bool && **True** if specified key is down. && key && string && Qualifier key to test for. && \[key...\] && string && Second qualifier key... \</evalcmd\>

Returns **True** if the specified qualifier *key* or keys are held down. If multiple keys are provided, all must be held down to return **true**.

Valid keywords are **none**, **shift**, **ctrl** and **alt**.

//<Example://>

    if (KeyDown("shift", "ctrl"")) { ... } // are both shift and ctrl are down?
