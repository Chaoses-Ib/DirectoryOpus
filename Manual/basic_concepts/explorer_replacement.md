# Explorer Replacement

One of the key features of Directory Opus is its *Explorer Replacement* mode.

\<WRAP round info\> To clarify exactly what we mean by Explorer Replacement:  
  
Whenever an action is taken that would ordinarily result in a File Explorer window opening, a Directory Opus window (Lister) will open instead. \</WRAP\>

##### Activating Explorer Replacement

Explorer Replacement mode is controlled by the options on the **[Launching Opus / Explorer Replacement](/Manual/preferences/preferences_categories/launching_opus/explorer_replacement.md)** Preferences page. Selecting any option other than **Don't replace Explorer** activates Explorer replacement mode.

##### Windows + E key

On Windows 10 and above, the <kbd>Win+E</kbd> is intercepted by a different process to Explorer Replacement, and can be set to open Opus even if replacement mode is disabled, from the [Launching Opus / From the Win + E hotkey](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_win-e_hotkey.md) Preferences page.

##### Getting to File Explorer when replacement is enabled

When Explorer Replacement mode is enabled, it is still possible to get to File Explorer if desired:

- From the Start Menu, select **Run** (or push <kbd>Win+R</kbd>) and enter *explorer.exe*
- Right*-*click on any folder and choose **Open in Explorer** from the context menu
- Click the pinned Explorer icon on the taskbar

##### Explorer replacement limitations

Even when Explorer replacement mode is enabled, there are some cases when Explorer will continue to open:

- Subject to the setting on the **[Launching Opus / Explorer Replacement](/Manual/preferences/preferences_categories/launching_opus/explorer_replacement.md)** page, a Lister may not open for all types of folder.
- A program that [specifically invokes Explorer](http://blogs.msdn.com/b/oldnewthing/archive/2007/04/30/2332224.aspx) may not be able to be intercepted by Opus (although many times it will).
- Opus will never open the Control Panel (or its various sub-pages) - they will always open in Explorer.

Opus does **not** replace the desktop (which is actually implemented by explorer.exe), nor does it replace the standard File Open / Save dialogs in other applications.

##### Explorer replacement in USB mode

Explorer Replacement requires changes to the Windows registry and so is generally unavailable when running a [USB exported version](/Manual/additional_functionality/exporting_to_usb.md) of Directory Opus, however there is an option to temporarily make the registry changes needed (which might work, depending on your user permissions, or it might not).
