\<evalcmd\> SysInfo && var && Value of the specified property. && property && string && Name of property to return. Available properties are:

|                  |                                                       |
|------------------|-------------------------------------------------------|
| **DarkMode**     | returns **True** if Opus is in dark mode              |
| **DarkModeApps** | returns **True** if other apps should be in dark mode |
| **MouseMonitor** | returns index of monitor the mouse is currently on    |
| **MousePosX**    | returns mouse x-coordinate                            |
| **MousePosY**    | returns mouse y-coordinate                            |
| **TouchInput**   | returns **True** if Windows is in tablet mode         |
| **USBInstall**   | returns **True** if Opus is running from a USB export |

\</evalcmd\>

Allows you to query the value of certain system properties.

//<Example://>

    if (SysInfo("MouseMonitor") == 0) { ... } // see if the mouse is on monitor 0
