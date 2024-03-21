# Backing up and Restoring Preferences

Opus stores its Preferences settings on disk, so backing up your Preferences can be as simple as making a copy of the files / folders in question. However Opus includes an integrated Backup tool that automates this process for you, and results in a single backup file that can be used to restore your Preferences in the event that Opus ever has to be reinstalled. If you ever install Opus on a new computer you can also use this to move your configuration across.

![](/Manual/images/media/13/prefs_backup.png) 

To access the *Backup and Restore Configuration* dialog, select the option from the ![](/Manual/images/media/13/prefs_menu.png) menu in the main Preferences dialog, or from the *Settings* menu in a Lister.

The four different modes of this dialog are:

- **Backup configuration**: make a backup of your current configuration.
- **Restore configuration**: restore a previously backed-up configuration.
- **[Export to USB](/Manual/additional_functionality/exporting_to_usb.md)**: if you have purchased the optional USB export license, export your Opus installation and configuration to a portable USB device.
- **Reset configuration**: reset your Opus configuration to the factory defaults. You'll be prompted to make a full backup of your existing configuration first.

This dialog isn't available when running an exported portable copy of Opus. If you wish to update the portable copy with a newer configuration from your normal install of Opus, simply export the normal install to the USB device again to overwrite it. (You will be asked whether you want to update just the program or both the program and the configuration.) If you wish to backup the configuration stored on a USB device you can simply archive the configuration directories below the DOPUS folder on the device.

Your Preferences, toolbars and file type settings are always backed up. There are several options available that determine what other parts of your configuration is included in the backup.

- **Backup images** includes any image files you are using in your configuration.
- **Backup sounds** does the same for any sound files. Note that both images and sounds are only backed up if they're located below your Opus configuration folder.
- **Backup miscellaneous data** will backup data that, while not forming part of your configuration as such, may still be important - things like your [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md), for example.
- **Backup local state data** will include data that may really only make sense on the local machine - things like your remembered window positions and so on. You'd want this for disaster recovery but not necessarily when moving your configuration to a new machine.
- **Backup currently open folder tabs** will include currently open windows and tabs in the backup. This is a subset of **local state data**, so it is only relevant if that is also on.

You are also given the option to encrypt the backup file, which you may wish to do to protect things like your stored FTP site passwords.

The same options (images, sounds, miscellaneous data and local state data) are also available when restoring a previously backed up configuration, as well as the **Replace existing configuration completely** option. If this option is not selected, the configuration you restore will be "merged" with your current configuration - if selected, the option causes Opus to delete your existing configuration before restoring the new one.
