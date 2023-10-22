# Startup

The settings on this page let you set Opus to run automatically when Windows starts up. You can also control what Listers are opened automatically when Opus starts, and whether Opus stays running in the background when no Listers are open.

The **Startup settings** section controls whether Opus runs on start up.

- **Launch Directory Opus automatically on system startup**: When Windows boots, Directory Opus will start running automatically. Having Opus always running means opening a Lister is much quicker, and it also lets you take advantage of configurable [system-wide hotkeys](/Manual/additional_functionality/system-wide_hotkeys.md) and [floating toolbars](/Manual/additional_functionality/floating_toolbars/RAEDME.md). Run-on-startup is implemented by adding a shortcut to the *Startup* program group in the Start menu.
- **Show introductory start window**: If this option is on, Opus will display a splash screen when it starts as long as no Listers are opened automatically. If Listers are opened on startup the splash screen will not be shown. The splash screen provides links that let you easily open a new Lister, access the Preferences system, etc.

Windows 8 and above add a significant delay before launching applications at startup. The **Remove Startup Delay** button lets you remove this delay. Changing this option affects all programs launched via the Start Menu startup folder, not just Opus, and the setting is in the registry rather than the Directory Opus configuration (so you'll need to change it on individual machines if desired). It's a Windows setting, not an Opus one - we just provide a convenient way to change it in Preferences. You can use the **Restore Startup Delay** button to turn it back on again if you've previously removed it.

The **Listers opened automatically when Directory Opus starts** section lets you control what Opus does when it starts. This applies when Opus runs on system startup and also when you run Opus by double-clicking the shortcut icon on the desktop or in the start menu. It doesn't affect what happens if Opus starts because of another action - e.g. double-clicking the desktop uses the settings in the [From the Desktop](launching_opus_from_the_desktop.md) page, whether Opus is already running or not.

- **Don't open any Listers**: No Listers will be opened. The splash screen will be shown if the Show introductory start window option is turned on.  
  \* **Open the Default Lister**: The Default Lister is opened.  
  \* **Open the Listers that were open when the program was last closed**: When Opus quits it remembers which Listers were opened, and restores them the next time it starts.
  - **Include virtual folders**: Virtual folders (like *Recycle Bin*) are included in the remembered set of Listers. If this is turned off only Listers showing real file-system paths (like *C:\\*) are remembered.  
    \* **Open a saved Lister layout**: Opens a saved [Lister layout](/Manual/basic_concepts/the_lister/layouts/RAEDME.md).  
    \* **Run a command**: Lets you enter a command line to be run when Opus starts up. This can be used to perform more complex actions including running external programs.

The **Shutdown Directory Opus when the last Lister closes **option lets you configure Opus to shutdown automatically once you close the last Lister. This makes Opus behave more like a traditional application that you run, use and then exit when finished with. We recommend that you keep Opus running in the background even when you're not using it as it makes it much quicker to open Listers, and means things like [system-wide hotkeys](/Manual/additional_functionality/system-wide_hotkeys.md) and [floating toolbars](/Manual/additional_functionality/floating_toolbars/RAEDME.md) can work, but if you don't want to use it like this you can turn this option on.
