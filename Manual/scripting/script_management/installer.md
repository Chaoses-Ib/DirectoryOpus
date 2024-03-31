# Script Installer

The *Install Script* function makes it easy to install new script add-ins in Opus, that you've e.g. downloaded from the [Opus resource center](https://resource.dopus.com).

To access the installer, select the **Install Script** function from the default **Settings** menu. If you're using old toolbars without that command in them, you can add it from the **Customize / Default Toolbars** tab. The raw command is `Prefs SCRIPTINSTALL`. You can also launch the installer via the *[Script Management]()* dialog.

The installer can install scripts in several different formats:

- Single script files (with a suffix like `.js` or `.js.txt`).
- Script [packages](../script_add-ins/script_package.md) (with a `.osp` suffix)
- Script installer files (with a `.opusscriptinstall` file).

When you **Share** a script from the *Script Management* dialog, Opus bundles it into a *script installer* file. These are ideal for sharing scripts as they bundle all the required files into one archive (including any [include files](../script_add-ins/include_files.md) the script needs). Provided Opus has been installed properly and isn't running off USB, they can also be installed by simply double-clicking the file.

The script installer window lists the scripts that are going to be installed. If a script provides a version number, this is shown along with the currently installed version number if an earlier version of the script exists. You can selectively turn scripts on and off in the installer in case a script package installs multiple scripts and you only want a particular one.

### Install Script Results

Once the script install is complete, Opus shows a summary of what was installed.

![](/Manual/images/media/13/script_install.png)

Any commands and/or columns that the new script adds are shown in the results dialog. The results dialog also makes it easy to try out the new script:

- For commands: Leave the results dialog open and go into *Customize* mode. You can drag the new commands directly out of the dialog and drop them on your toolbars.
- For columns: Drag the columns from the dialog and drop them on a *Details* mode file display to add the new columns to the Lister.
