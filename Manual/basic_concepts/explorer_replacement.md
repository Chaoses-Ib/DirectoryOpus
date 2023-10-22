# Explorer Replacement

One of the key features of Directory Opus is its *Explorer Replacement* mode. To clarify exactly what we mean by Explorer Replacement:

*    whenever an action is taken that would ordinarily result in an Explorer window opening, a Directory Opus window (Lister) will open instead.*

That's to say, Opus does **not** replace the desktop (which is actually implemented by explorer.exe), nor does it replace the standard File Open / Save dialogs in other applications.

Explorer Replacement mode is controlled by the options on the **[Launching Opus / Explorer Replacement](/Manual/preferences/preferences_categories/launching_opus/explorer_replacement.md)** Preferences page. Selecting any option other than **Don't replace Explorer** activates Explorer replacement mode.

When Explorer Replacement mode is enabled, it is still possible to get to Explorer if desired:

- From the Start Menu, select **Run** and enter *explorer.exe*
- Right*-*click on any folder and choose **Open in Explorer** from the context menu
- On Windows 7 and above, click the pinned Explorer icon on the taskbar

Please note that even when Explorer replacement mode is enabled, there are some cases when Explorer will continue to open:

- Subject to the setting on the **[Launching Opus / Explorer Replacement](/Manual/preferences/preferences_categories/launching_opus/explorer_replacement.md)** page, a Lister may not open for all types of folder.
- A program that [specifically invokes Explorer](http://blogs.msdn.com/b/oldnewthing/archive/2007/04/30/2332224.aspx) may not be able to be intercepted by Opus (although many times it will).
- Except in Windows XP, Opus will never open the Control Panel (or its various sub-pages) - they will always open in Explorer.

Explorer Replacement mode is generally unavailable when running a [USB exported version](/Manual/additional_functionality/exporting_to_usb.md) of Directory Opus.
