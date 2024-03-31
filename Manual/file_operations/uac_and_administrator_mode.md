# UAC and Administrator Mode

UAC ([User Account Control](http://en.wikipedia.org/wiki/User_Account_Control)) is a Windows security feature. It aims to make it much more practical to run as a standard user, by allowing administrator operations to be performed by temporary elevations of access permissions.

When UAC is enabled (which it is, by default), users and the programs they launch will have standard user privileges by default. This means that important operating system locations (like the *Windows* folder) and registry keys are protected against accidental or malicious modification - in order to make changes to these locations, you need to *elevate* the task by means of a UAC prompt.

![](/Manual/images/media/13/user_account_control.png)

### Explorer gets treated differently

Unfortunately Microsoft somewhat [botched](http://www.pretentiousname.com/opus9/page4.html#vistauac) the implementation of UAC in Explorer. Vista was widely derided for the sheer number of UAC prompts you needed to click through to perform routine or mundane tasks. Simply creating a folder could result in four individual prompts, leading many people to simply turn UAC off altogether.

Since Windows 7, Microsoft over-reacted to the criticism and have dramatically toned down UAC - unfortunately to the detriment of your system security. The default UAC settings (which use a [white-list](http://www.pretentiousname.com/misc/win7_uac_whitelist2.html) to prevent any UAC prompts at all for Explorer and other Windows components) reduce it to the mere appearance of a security system - and at the same time, disadvantaging other third-party tools that don't have the ability to be white-listed.

We have always viewed UAC as a commendable (if poorly-executed) attempt to improve the security of Windows, and we recommend both leaving it set to **Always notify** in the Windows security settings. Opus natively supports UAC, in a much more sensible way than Explorer, and you won't find performing administrative tasks in Opus difficult or irritating at all.

### Performing administrative tasks in Opus

When performing a file operation in a protected location, like *C:\Program Files*, Opus will display a UAC prompt as in the screenshot above. It tries to be smart about this - it will only prompt once per function, unlike Explorer which can sometimes prompt up to four times for the one operation.

### Elevating for a period of time

If you are performing multiple administrative tasks, you can use the **Administrator Mode** function to temporarily elevate the current Lister.\<WRAP\>

To activate Administrator mode, click the **Admin** button on the default toolbar. Opus will display a dialog that lets you specify a timeout after which Administrator mode is automatically deactivated. This is for security reasons, as it avoids the risk of accidentally leaving a Lister elevated longer than necessary.

![](/Manual/images/media/13/admin_mode_dialog.png)

Select the timeout, and click OK. Opus will then display a UAC prompt to elevate, and after that the Lister itself will remain elevated for the specified period (or until you turn the mode off manually). The title bar of the window changes to say **Administrator** to indicate admin mode is in effect.

(Note that if you ever see **ADMINISTRATOR** in the title bar, it means the whole process is elevated - something we [don't recommend](https://resource.dopus.com/t/why-not-to-run-opus-as-administrator-under-uac/9102).)

Any operations you perform in an Administrator mode Lister will be automatically elevated - no further UAC prompts will need to be shown. Note though that any programs you launch from that Lister will also be elevated.

### Elevation in functions

You can configure a toolbar button or hotkey that launches an external program to launch the program elevated using the **@admin** [command modifier](/Manual/customize/creating_your_own_buttons/command_modifiers.md).
