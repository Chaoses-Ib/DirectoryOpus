# Installing and Registering

Like many programs, Directory Opus uses the industry-standard InstallShield installer to manage installation. Begin the installation by double-clicking the setup program (normally called *DOpusInstall.exe*).

The installer is also an updater - it can install Opus on a new machine or it can install a new version over an existing version. (When updating, do *not* uninstall the old version first, unless you wish to reset your configuration to the factory defaults.) The same installer works with both 32-bit (x86) and 64-bit (x64) Windows, automatically selecting the appropriate components for your computer. The installer also works for both Light and Pro editions of Opus and for both evaluation and purchased licences. If you get a new licence, you only need to install the licence itself (using the Licence Manager - see below) and do not need to re-install the whole program.

Once the installation process is complete, you will be given the option to start Opus immediately - the installer will also place a shortcut icon on your desktop that you can use to launch Opus. When you run Opus for the first time, the **Directory Opus Initialisation Wizard** will asked you a few questions that help define your initial configuration. We recommend that you choose the default settings but of course you don't have to, and all these settings can be modified later through the program's Preferences dialog.

![](/Manual/images/media/initialwizard.png)

There are seven choices you must make in this wizard; one per page:

- **Language**: Directory Opus normally defaults to English but you can switch to another language here. You can also change language later on from the **[Display / Language](/Manual/preferences/preferences_categories/display/language.md)** page in Preferences.
- **Edition**: Directory Opus comes in two editions - Pro and Light. During your initial evaluation period you can choose to trial Opus in either "mode". You can switch edition later on using the **Licence Manager** (see below). See the [GP Software](http://www.gpsoft.com.au/DScripts/redirect.asp?page=prolite) website for more information on the differences between the editions.
- **Launch On Startup**: Select this option to have Directory Opus run automatically on Windows startup. This is recommended mainly because access to Opus is much quicker if it's already in memory - opening a new window via double-click on the desktop or a hotkey like **Windows+E** will be almost instantaneous if Opus is already running in the background. You can modify this option at any time from the **[Launching Opus / Startup](/Manual/preferences/preferences_categories/launching_opus/launching_opus_on_startup.md)** page in Preferences.
- **Explorer Replacement**: Select this option if you want Directory Opus to replace Explorer. If you turn this on then double-clicking on a folder on the desktop, or performing any other action that normally opens an Explorer window, will cause Opus to open instead. See the page on [Explorer Replacement](/Manual/basic_concepts/explorer_replacement.md) mode for more information. You can modify this option at any time from the **[Launching Opus / Explorer Replacement](/Manual/preferences/preferences_categories/launching_opus/explorer_replacement.md)** page in Preferences.
- **FTP Handling**: Select this option if you want Opus to register itself as the default FTP handler. If this is selected then clicking on an **ftp://** link will cause the FTP site to open in an Opus Lister rather than in your web browser or other FTP client. You can modify this option at any time using the **[Miscellaneous / Windows Integration / Make Directory Opus the default handler for FTP sites](/Manual/preferences/preferences_categories/miscellaneous/windows_integration/RAEDME.md)** option in Preferences.
- **ZIP Handling**: If this option is selected then Opus will register itself as the default handler for ZIP files. Double-clicking on a **.zip** file will cause an Opus Lister to open showing the contents of the archive (and you can then view, extract, add, delete, etc. files within the archive using Opus). You can modify this option at any time using the **[Zip & Other Archives / Zip Files / Make Opus the system default handler for Zip files](/Manual/preferences/preferences_categories/zip_and_other_archives/zip_file_options.md)** option in Preferences.
- **Picture & Sound Double-Click Handling**: If you enable this option, then double-clicking on an image or sound file (that Opus recognizes) in Opus will cause the internal viewer or player to be used rather than the normal default handler for that file type. This option doesn't modify any registry settings and doesn't actually change the default handlers for these file types in the system - instead, it enables an override that's only effective inside of Opus itself. You can modify these options at any time from the **[File Operations / Double-click on Files](/Manual/preferences/preferences_categories/file_operations/double-click_files/RAEDME.md)** page in Preferences.

Directory Opus uses a certificate-based licencing system. When you purchase Opus, or register for a 60 day evaluation, you will receive a small text file that is your program certificate. This contains (in encoded form) data about your Opus registration, including enabled features, number of installs allowed and in the case of an evaluation licence, the expiry date. To activate your copy of Directory Opus you need to install the certificate using the program's **Licence Manager** function. The Licence Manager window will open by itself a short time after you run the program, but you can also invoke it at any time from the **Help** menu.

![](/Manual/images/media/licman1.png) 

Directory Opus comes with a special program certificate called the **Default Evaluation Certificate**. This certificate lets you evaluate Directory Opus for up to 30 days from the date you first run the program. During this evaluation period you can switch back and forth between the Pro and Light editions using the **Switch Version** command in the Licence Manager.

If you'd like to trial the Pro edition for longer than the initial 30 days, you can register for a free 60-day evaluation by clicking the **Request Free Evaluation** button in the Licence Manager.

![](/Manual/images/media/licman2.png) 

Enter your name and email address, and click the **Register** button and Opus will automatically contact our servers over the Internet and download an evaluation certificate for you. Alternatively, you can request an evaluation certificate through our [website](http://www.gpsoft.com.au/DScripts/evalrequest.asp).

If you have purchased Directory Opus, or registered through the website for an evaluation, and you have received your certificate via email, simply double-click on the attached certificate file to install it. Alternatively, use the **Install New Certificate** button in the Licence Manager.

![](/Manual/images/media/licman3.png) 

  
Use the **Load** button if you have your certificate stored on disk as a **.txt** or **.opuscert** file. You can also copy it to the clipboard, and then click the **Paste** button to paste it into the Licence Manager.

The **Retrieve** button can be used if you have previously purchased Opus and wish to install it on a new machine - by providing your registration code or product token and registered email address you can retrieve your certificate from our servers over the Internet. You can also retrieve a lost registration code and certificate through our [website](http://www.gpsoft.com.au/DScripts/lostcode.asp).

The final page in the Licence Manager is the **Register Product Token** page. Product tokens are issued by our resellers, and you can use this page to register a product token to receive your full program certificate. You can also register a product token through our [website](http://www.gpsoft.com.au/DScripts/regboxed.asp).
