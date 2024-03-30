# SysInfo

The **SysInfo** object is created by the **[DOpusFactory](dopusfactory.md).SysInfo** method. It lets scripts access miscellaneous system information that may not be otherwise easy to obtain from a script.

<table>
<thead><tr><th>
Method Name</th><th>
Arguments</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
DarkMode</td><td>

*none*</td><td>

*bool*</td><td>

Returns true if Dark Mode is on within Opus, and false otherwise.

May differ from **DarkModeApps** if Opus is configured to override the system-wide setting, or on older versions of Windows which did not have Dark Mode.
</td></tr><tr><td>
DarkModeApps</td><td>

*none*</td><td>

*bool*</td><td>

Returns true if Windows is configured to run applications in Dark Mode, and false otherwise.

Always returns false on older versions of Windows which did not have a Dark Mode.
</td></tr><tr><td>
DPI</td><td>

*none*</td><td>

*int*</td><td>
Returns the DPI that Opus is currently running in (e.g. 96 DPI is 100% scaling).
</td></tr><tr><td>
FindProcess</td><td>

*string*</td><td>

*int*</td><td>

Allows you to test if a named process is currently running, and returns the process's ID if so. If the process isn't running **0** is returned. You can use wildcards or (by prefixing the pattern with **regex:**) regular expressions.
</td></tr><tr><td>
Language</td><td>

*none*</td><td>

*string*</td><td>
Returns a string indicating the language Opus is currently using.
</td></tr><tr><td>
Monitors</td><td>

*none*  
or  
*int:index*</td><td>

**[Vector](vector.md):[Rect](rect.md)**   
or  
**[Rect](rect.md)**</td><td>

If called with no arguments, returns a **[Vector](vector.md)**of **[Rect](rect.md)** objects which provide information about the positions and sizes of the display monitors in the system.

If called with an index argument, returns a single **[Rect](rect.md)** with the information for just a particular monitor.

The **WorkAreas** method, documented below, is sometimes what you should use instead of this.
</td></tr><tr><td>
MouseMonitor</td><td>

*none*</td><td>

*int*</td><td>
Returns the index of the monitor the mouse pointer is currently positioned on.
</td></tr><tr><td>
MousePosX</td><td>

*none*</td><td>

*int*</td><td>
Returns the current x-coordinate of the mouse pointer.
</td></tr><tr><td>
MousePosY</td><td>

*none*</td><td>

*int*</td><td>
Returns the current y-coordinate of the mouse pointer.
</td></tr><tr><td>
ShadowBorder</td><td>

*none*</td><td>

**[Rect](rect.md)**</td><td>

Returns a **[Rect](rect.md)** giving the size of the invisible border around windows.

On some operating systems (e.g. Windows 10), windows may be larger than they appear: Beyond the visible edge is a border that is part of the window but invisible. This border exists for legacy compatibility, allowing window frames to appear thin while providing something thick enough to resize with the mouse.

You can usually ignore the border but it is important when positioning windows next to each other, or to screen edges, where ignoring it results in gaps between windows.

The **Rect** returned by this method is unusual: The **left**, **right**, **top** and **bottom** properties do not represent the coordinates of a rectangle but rather the width of borders (if any) on each side of a window. As a consequence, the **width** and **height** properties of the **Rect** are meaningless.

On Windows 10, the top border is typically zero and the others are usually several pixels thick. The thickness varies by OS version, system DPI, and other factors; you should not store it to disk as it may not be correct for the system that loads it.

This property is relatively expensive to calculate. You should not, for example, call the method once for each side; instead, call it once and store the **Rect** in a variable, then query that for each side.
</td></tr><tr><td>
SystemDPI</td><td>

*none*</td><td>

*int*</td><td>

Returns the DPI that the system is currently running in (e.g. 96 DPI is 100% scaling). This will normally be the same as the **DPI** value, but if the system DPI has been changed and Opus has not been restarted they can be different.
</td></tr><tr><td>
TouchInput</td><td>

*none*</td><td>

*bool*</td><td>

Returns **True** if the system is currently using touch input.
</td></tr><tr><td>
USBInstall</td><td>

*none*</td><td>

*bool*</td><td>

Returns **True** if Opus is running from a [USB export](/Manual/additional_functionality/exporting_to_usb.md).
</td></tr><tr><td>
WorkAreas</td><td>

*none*  
or  
*int:index*</td><td>

**[Vector](vector.md):[Rect](rect.md)**   
or  
**[Rect](rect.md)**</td><td>

Similar to the **Monitors** method, documented above, except it returns the *work area* of each monitor rather than the full monitor area.

A monitor's *work area* is the monitor's rectangle minus the Windows Taskbar and any other *app bars* (which can include docked toolbars created by Opus, or similar things added by other software). If a monitor does not have a Taskbar or other app bar docked to it, its work area will be the same as its full rectangle.
</td></tr></tbody>
</table>

