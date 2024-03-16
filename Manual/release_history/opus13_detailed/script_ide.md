##### Directory Opus 13 - Detailed release notes

# Script IDE

- Script Management dialog:
  - Dialog for managing scripts is now standalone instead of in Preferences.
  - The new Script Editor (see below) can be accessed double-clicking a script, or via the Edit button.
  - Cog buttons appear next to scripts that support configuration.
  - Changes in the dialog (e.g. disabling a script) take effect immediately. No need to click OK or Apply.
- Script sharing:
  - Share button makes it easy to share your scripts. The selected script (either standalone or package) and any include files it needs will be bundled automatically into a Opus Script Install file.
  - Opus Script Install files can be installed via the dialog, or via Settings \> Install Script from the main window. This also works with standalone scripts and script packages from older versions.
  - The script installer will warn you if a script requires a newer version of Opus, and displays a summary of commands and columns the script will add.
  - After installation, you can drag new commands or columns to a toolbar or file display from the Install Results dialog.
- Script editor:
  - New, integrated editor for writing scripts and managing their resources.
  - Multi-document, tabbed interface.
  - Lets you edit standalone scripts, script packages, and their resources.
  - Built-in dialog and string (localization) resource editors.
  - Easily convert standalone scripts to packages.
  - Add and manage images, icon sets and help files within script packages.
  - Pre-supplied snippets list to add common code to your scripts via drag & drop or copy/paste.
  - You can add your own code to the snippets list for future reuse.
  - Option to use external text editor, if desired. (IDE monitors files for changes and updates automatically.)
- Script modules:
  - Large scripts can now be split into multiple "modules", instead of a large file.
  - Module filenames must begin with the main script's name, followed by the module name and a .osm suffix.
  - //<Example://> "MyScript.js" might have a module file called "MyScript.js.FirstModule.osm".
  - The Script IDE lets you create new modules for an existing script.
- Include files:
  - Can be created via the New Script dialog.
  - "Include files" let you share code (e.g. helper functions) between separate scripts, without having multiple copies of the same code.
  - Include files must have a name beginning with "inc\_".
  - Include files can implement the OnInitIncludeFile method to provide information about them to the user, but this is not required.
  - To use an include file from another script, add a line at the very top of the script: @include \<includefile\>.
  - The minimum required version of the include file can also be specified.
  - The Script IDE lets you select include files for scripts using a GUI, taking care of most details for you.
- Commands:
  - \<ib:inline-code\>`Prefs INSTALLSCRIPT`\</ib:inline-code\>
  - \<ib:inline-code\>`Prefs SCRIPTS`\</ib:inline-code\> -- Can open the Script Management dialog, select a script and (if applicable) open its configuration UI.
    - Script is specified by filename and usually uses a wildcard so it works whether the extension has ".txt" on the end or not.
    - The command editor can generate the proper command and wildcard for you.
    - //<Example://> \<ib:inline-code\>`Prefs SCRIPTS=AlbumDoubleClick.vbs*`\</ib:inline-code\>
  - \<ib:inline-code\>`Prefs SCRIPTEDIT`\</ib:inline-code\> -- Can open the Script IDE for a specified script.
    - Same filename and wildcards as \<ib:inline-code\>`Prefs SCRIPTS`\</ib:inline-code\>, above.
    - //<Example://> \<ib:inline-code\>`Prefs SCRIPTEDIT=AlbumDoubleClick.vbs*`\</ib:inline-code\>
- Miscellaneous:
  - When creating a new script, there is now the option to create it as a script package. (Packages allow multiple scripts and other resources to be included in a single file.)
  - By default, the New Script dialog now creates template code for commands and columns using the newer (Opus 12) OnAddCommands / OnAddColumns syntax.

------------------------------------------------------------------------

Next: [File Types](/Manual/release_history/opus13_detailed/file_types.md)
