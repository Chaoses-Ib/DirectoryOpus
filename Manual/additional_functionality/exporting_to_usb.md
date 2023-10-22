# Exporting to USB

If you purchase the optional USB export licence, you are able to export your installation and configuration to a USB device. This lets you make a "portable" version of Opus that you can run on other computers without needing to install Opus on them. The portable version is entirely self-contained on the export device, and it doesn't make any registry or other changes to the system it's run on.

The USB export feature is an extra cost because it actually grants you an extra licence to run Opus simultaneously on another machine. If you didn't select it when you purchased Opus, you can add it on at any time from the [My Account](https://www.gpsoft.com.au/DScripts/licencemanager.asp) page on the GP Software website. You can check if the USB export feature is enabled from the **Licence Manager** (from the **Help** menu).

To begin the USB export procedure, select the **Backup and Restore** command from the **Settings** menu. Click the **Export to USB Flash Drive** option, and click **Next** to continue.

![](/Manual/images/media/usb_export.png)

The dialog displays a list of your USB devices. As well as normal flash drives and external USB hard drives, Opus also supports [U3](https://en.wikipedia.org/wiki/U3) devices (although this standard is more-or-less defunct now) - any U3 devices will be indicated with a different icon. Opus also supports devices with the [PortableApps](http://portableapps.com/) menu system installed on them.

You can choose several different ways of exporting to the USB drive:

- The default behaviour is to export Opus to the selected drive. The program and configuration files will be copied to a new folder in the root of the selected device.
- The **Use this drive as a dongle** option lets you export to a different location - the selected USB drive will only be used to validate the exported licence. For example, a [VeraCrypt](https://en.wikipedia.org/wiki/VeraCrypt) encrypted container does not appear to Opus as a USB drive, and so you would not ordinarily be able to select it for export. Using the *dongle* option, you can export Opus to the encrypted drive, and the "parent" USB drive itself will only be used for licencing purposes.
- U3 devices will show in the list as two separate entries - the U3 device (with a U3 icon), and a normal USB drive. These represent the two separate partitions on a U3 device. If you want to make a **.u3p** bundle (which can be installed into the U3 program launcher), you should select the U3 device entry. (Note: U3 is only available on 32-bit computers, due to limitations of the discontinued U3 software itself.)
- [PortableApps](http://portableapps.com) devices are detected automatically. When you select a device with PortableApps installed on it, Opus will automatically create the necessary folder structure to integrate the portable version into the PortableApps launcher menu.

Select the drive you want to export to, and **click** Next to continue. At this point, if you selected the **Use this drive as a dongle** option, you will be prompted for the real location to export Opus to.

You will next be given three choices as to which version(s) of Directory Opus to export:

- **Directory Opus 32-bit (x86)**: This will export a 32-bit copy of Directory Opus. The exported copy will run on both 32-bit and 64-bit Windows but will have slightly limited functionality on 64-bit. (See above.)
- **Directory Opus 64-bit (x64)**: This will export a 64-bit copy of Directory Opus. The exported copy will only run on 64-bit versions of Windows; it will not work at all on 32-bit versions of Windows.
- **Both versions**: This will export both a 32-bit copy and a 64-bit copy of Directory Opus to the same device. The small DOPUS.EXE program placed in the root of the device will automatically select the best copy when you run it. This is the recommended option unless you need to minimize space usage or know that you'll always be using the USB stick with either 32-bit or 64-bit computers.

You will also be asked to select which elements to include with the exported copy, allowing you to reduce space usage and the duration of the export process by excluding unwanted components:

- **Plugins**: Choose which viewer and VFS plugins to include. Only "USB safe" plugins are listed; that means plugins designed not to leave anything behind on the host machine (e.g. in the registry) when running from USB. Some third-party plugins are not USB safe and will not be listed.
- **Languages**: English is always included, but this lets you select additional language files to include if desired.
- **Help files**: Includes this help file.
- **Current configuration**: You can choose to export your configuration as well as the program. If this option is not selected, the exported version will begin with the default configuration. You can also choose which elements of your configuration to include.

You may be offered the option to export image and sound files used by your configuration. This only applies to files stored below the appropriate **Images** and **Sounds** Opus configuration directories. You can locate these directories by typing the **/dopusdata** [folder alias](/Manual/basic_concepts/the_lister/navigation/aliases.md) into the location field. (They may also be stored below the shared **/dopusglobaldata** directory. Elements of the private and shared configurations are merged when exporting to USB.) Images or sounds located in other places will not be copied to the USB drive; the configuration can still point to them, but the exported copy will obviously only be able to load them if they exist in the same place on the computer you run the exported copy of Opus on.

The final confirmation page displays the total size required on the export drive. Click **Next** to proceed with the export.

Normally **[Explorer Replacement](/Manual/basic_concepts/explorer_replacement.md)** mode is not available when running the USB version. This is because Explorer Replacement mode requires making changes to the system registry, including some changes that can only be made as an administrator (e.g. from the program installer). However, you can enable a limited form of **Explorer Replacement** mode for the USB version by editing the INI file that is created alongside the portable launcher. When Explorer Replacement mode is turned on in the USB version, some (but not all) of the modifications to the system registry are made, and the old values restored automatically once the portable version exits. You may find that Explorer Replacement mode does not work quite as well in the portable version as in the normal version of Opus - for example, folders launched by some third-party applications may continue to open in Explorer.

The INI file can be found (or created) in the same folder as the USB launcher (called *DOPUS.ini*, normally in the root of the device) for a normal USB export, and in the **F:\PortableApps\DirectoryOpusPortable\App\AppInfo** folder for a PortableApps export (called *DirectoryOpusPortable.ini*). Below

is an example of the format of this INI file.

    # This is an example INI file for the Directory Opus portable launcher.
    #
    # The options you can set in this INI file are:
    #
    # AllowExplorerReplacement: Determines whether the Explorer Replacement option is available in the portable version.
    # "true" or "false" (default "false")
    #
    # RunFromTempFolder: If AllowExplorerReplacement is true, determines whether the launcher is copied to the %TEMP% folder
    # on the host system and run from there. Allows more secure clean-up of Explorer Replacement registry changes.
    # "true" or "false" (default "true")
    #
    # AutoLister: Enable or disable 'auto-Lister' semantics when the portable version is started.
    # "true" or "false" (default "true")
    #
    [DirectoryOpusPortable]
    AllowExplorerReplacement=false
    RunFromTempFolder=true
    AutoLister=true
