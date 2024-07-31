\<evalcmd\> SysInfo && var && Value of the specified property. && property && string && Name of property to return. Available properties are:

|                  |                                                                                                                                                                                                                                           |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **DarkMode**     | returns **True** if Opus is in dark mode                                                                                                                                                                                                  |
| **DarkModeApps** | returns **True** if other apps should be in dark mode                                                                                                                                                                                     |
| **DPI**          | returns the DPI that Opus is currently running in (e.g. 96 DPI is 100% scaling).                                                                                                                                                          |
| **Language**     | Returns a string identifying the language Opus is currently using.                                                                                                                                                                        |
| **MouseMonitor** | returns index of monitor the mouse is currently on                                                                                                                                                                                        |
| **MousePosX**    | returns mouse x-coordinate                                                                                                                                                                                                                |
| **MousePosY**    | returns mouse y-coordinate                                                                                                                                                                                                                |
| **SystemDPI**    | returns the DPI that the system is currently running in (e.g. 96 DPI is 100% scaling). This will normally be the same as the **DPI** value, but if the system DPI has been changed and Opus has not been restarted they can be different. |
| **TouchInput**   | returns **True** if Windows is in tablet mode                                                                                                                                                                                             |
| **USBInstall**   | returns **True** if Opus is running from a USB export                                                                                                                                                                                     |
| **Version**      | returns the full Opus version string                                                                                                                                                                                                      |
| **VerHigh**      | returns the major ("high") Opus version number (e.g. 13)                                                                                                                                                                                  |
| **VerLow**       | returns the minor ("low") Opus version number (e.g. 6)                                                                                                                                                                                    |
| **VerBeta**      | returns the Opus beta release number (or 0 for stable releases)                                                                                                                                                                           |
| **VerBuild**     | returns the current build number                                                                                                                                                                                                          |

\</evalcmd\>

Allows you to query the value of certain system properties.

//<Example://>

    if (SysInfo("MouseMonitor") == 0) { ... } // see if the mouse is on monitor 0
