##### Directory Opus 13 - Detailed release notes

# Miscellaneous Scripting

#### General

- See [Script IDE](script_ide.md) for details of the new script editor and management UIs.
- Some scripting changes are mentioned in other sections instead of here.

------------------------------------------------------------------------

#### System settings

- New OnSystemSettingChange event, fires when system settings change. SystemSettingChangeData.type provides the change type:
  - "Environment" when environment variables change.
  - "UserInteractionMode" when touch/mouse input mode changes at the OS level.
  - "SpacingScheme" when Opus switches to a new UI spacing scheme, potentially in reaction to "UserInteractionMode". SystemSettingChangeData.name provides the new scheme name.
  - "ColorSet" when Opus switches between dark and light modes.
  - "Theme" when the system theme (Visual Style) changes.
  - "DWMComposition" when DWM Composition is turned on or off.
  - "DWMColorization" when DWM window frame colors change.
  - System WM_SETTINGCHANGE messages also trigger this event, with other type values defined by Microsoft. These may include "WindowMetrics", "intl", "Policy", "ConvertibleSlateMode", "SystemDockMode", and more.
- SysInfo.DarkMode returns true if Opus is in dark mode.
- SysInfo.DarkModeApps returns true if dark mode is on (for applications) at the OS level.
- SysInfo.DPI returns the DPI scaling applied to the Opus process.
- SysInfo.SystemDPI returns the current system DPI (may differ if it changed since Opus launched).
- SysInfo.TouchInput returns true if the system is in touch mode at the OS level.
- SysInfo.USBInstall tells you if Opus is running from a portable install (USB Export).
- DOpus.SpacingScheme returns the name of the current UI spacing scheme within Opus (if any).

------------------------------------------------------------------------

#### Paths

- Path.Resolve method, which is like the older DOpus.FSUtil.Resolve, but modifies a Path object in-place.
- Path.Normalize which normalizes the path string by:
  - Converting all forward-slashes to back-slashes (for a normal path - vice versa for a URL).
  - Collapsing duplicate slashes to a single slash (except where needed in UNC paths and URLs).
- Path.Normalize is called automatically when a string is assigned to a Path object, so you don't normally need to call it manually.
- Path.ToUNC converts from a mapped network drive letter path to a UNC path.
- FSUtil.Exists can now be given a wildcard in the final path component, if the "w" flag is also specified.
- FSUtil.PathType method tells you a path's type ("shell", "filesys", "ftp", "zip", "mtp", "lib", "coll", "plugin").

------------------------------------------------------------------------

#### Dates

- Opus Date objects can now be created directly from JScript Date objects.
- Date.Set method now accepts a Unix epoch time directly.
- Date.ToEpochTime() method added to convert the other way.
- Improved logic of Date.Add() and Date.Sub() methods when adding/subtracting results in an invalid day (e.g. subtracting 1 month from a date on the 31st where the previous month only has 30 days).

------------------------------------------------------------------------

#### File change notification

- Dialog.WatchDir(\<id\>, \<dir\>, \<flags\>)
  - Let scripts monitor a folder or file for changes via a dialog.
  - Sends a "dirchange" Msg event, with "control" set to the specified change id.
  - \<id\> is a user-assigned id.
  - \<dir\> is the full path to a filesystem folder, or a file if the "i" flag is set.
  - \<flags\> are:
    - f - Monitor for file change in folder (e.g. file created).
    - d - Monitor for directory change in folder (e.g. directory created).
    - r - Recursive - monitor sub-folders.
    - a - Monitor for file attribute changes.
    - s - Monitor for file size changes.
    - w - Monitor for last write time changes.
    - i - Monitor a single file rather than a folder.
- Dialog.CancelWatchDir(\<id\>)
  - Cancels monitoring set up by previous WatchDir call.
  - \<id\> is the ID of the previous watch, or "\*" to cancel all.
- FSUtil.WatchChanges and FSUtil.CancelWatchChanges methods let script add-ins monitor a folder or a file for changes without a dialog:
  - When a change occurs, the new OnFilesystemChange event is triggered, with a FilesystemChangeData argument.
  - FilesystemChangeData.id provides the ID of the watcher that changed.
  - Arguments are the same as for Dialog.WatchDir and Dialog.CancelWatchDir, mentioned above.

------------------------------------------------------------------------

#### Taskbar notifications

- DOpus.Notify(\<title\>, \<msg\>, \<flags\>)
  - Displays a system notification, in the corner of the screen.
  - \<title\> and \<msg\> are text strings displayed to the user.
  - \<flags\> can be "n" to request the notification does not trigger a sound.
- Dialog.NotifyIcon(\<method\>,\<arguments...\>)
  - Allows script dialogs to add an icon to the system taskbar notification area.
  - Only one icon per dialog is supported.
  - \<method\> is one of:
    - "add" - Adds icon. Arguments: \<icon\>,\<tooltip\>.
    - "update" - Updates icon or tooltip. Arguments: \<icon\>,\<tooltip\>
    - "remove" - Removes icon. (No arguments.)
    - "notify" - Displays notification message. Arguments: \<title\>,\<msg\>,\<flags\>, same as DOpus.Notify, above.
  - For "add", both \<icon\> and \<tooltip\> are optional if the dialog has been assigned "icon" and "title" properties.
  - For "update", both \<icon\> and \<tooltip\> are optional.
  - For "notify", \<flags\> are optional.
  - Mouse events on the taskbar icon will generate "click", "dblclk" and "rclick" Msg events with the control property set to "notifyicon".
  - The icon is removed automatically when the dialog closes.

------------------------------------------------------------------------

#### Dialogs

- Msg.buttons property tells you which mouse buttons ("left", "right", "middle") were down when the message was generated.
- New Markup Text Controls allow dialogs to use basic markup, including hyperlinks, bold, italics and font colors.
  - Added through the dialog editor.
  - Icon property can be set to display an Info, Help, Warning or Link, to display different icons on the left of the control.
  - Hyperlinks generate Msg "click" event. Msg.value has the link ID (for when a single control has multiple links).
- New "shared width" and "shared height" resizing options which let two or more controls that share the width or height of the dialog.
- New "text" resizing option for Markup and Static text controls.
  - When combined with "width" resizing, causes the control to automatically adjust its height as necessary to show the whole text.
  - Controls below it automatically move up or down.
- Edit controls have a new "cuetext" property which lets you get or set their cue text at runtime.
- Empty edit controls now continue to show their cue text when they have focus, until something is typed.
- Dialog titles can be changed at runtime using the Dialog.title property.
- Tab control labels can be changed at runtime using the Control.label property. (E.g. \<ib:inline-code\>`Control.label(0) = "tab 1";`\</ib:inline-code\>)
- Control.style now works for dialogs inside tab controls.
- Fixes for dialog editor language overlays.

------------------------------------------------------------------------

#### Filter objects

- New Filter object to work with filters, such as used by Tools \> Find Files \> Advanced.
- DOpusFactory.Filter() -- Method. Create a new filter object.
- Item.MatchFilter() -- Method. Tests a file or folder against a filter.
- Command.SetFilter() -- Method. Associates a filter with a Command object.
- Command.ClearFilter() -- Method. Removes a previously associated filter.
- Scripts can run the "Select FILTER" command to use the associated filter.
- Scripts can also run "Select FILTERDEF ..." to define the filter on command line. (Described in more detail elsewhere.)

------------------------------------------------------------------------

#### Miscellaneous

- Added "duration" and "durationh" script column types. Displays the provided (integer) value as a duration:
  - Value represents the number of seconds.
  - "duration" only shows hours if the value is large enough to need them.
  - "durationh" always shows hours, even if they are zero.
- Vector.Reverse() -- Method. Reverses the order of elements.
- Tab.dest -- Property. Returns true if the tab is a destination.
  - There are situations where a tab is neither source nor destination, so the "source" property isn't always sufficient on its own.
  - Tab.source and Tab.dest are now always false for inactive (hidden) tabs. (Previously, inactive tabs returned stale information from the last time they were active.)
- DOpus.Listers.ToFront() -- Method. Moves one or more windows to the front.
  - Accepts a window handle or a vector of window handles.
  - The last window will be on top of the others. The rest will stack below it, in reverse order.
- Lister.WindowState -- Property. Provides window state ("min", "max", "hidden", "normal").
- Lister.ViewPaneFile -- Property. Provides path of file (if any) currently in the viewer pane.
- Viewer.ParentLister -- Property. Provides the Lister (if any) which launched the standalone viewer.
- Viewer.ParentListerLinked -- Property. Returns true if the viewer is Lister-Linked. (See [Viewer](#Viewer), Lister-Linked viewers.)
- Format.group_by -- Property. Now works with script columns.
- Item.nested -- Property. True if the file or folder is under an expanded folder. (See [File Display](#FileDisplay), Expandable folders.)
- ItemCollection.RemoveNested() -- Method. Removes any nested items from the collection, and returns the number removed.
- Favorites object:
  - When adding a new separator using the "sep" keyword, heading text can be given as in "sep:heading text".
  - Separator items have a SetHeading() method which lets the heading be modified.
- StringTools.LanguageStr -- Method. Returns the translated version of a string. (Only for supported strings.)
- StringTools.MakeLegal -- Method. Replaces characters which are invalid in a filename or path.
- StringTools.RemoveDiacritics() -- Method. Removes things like accents from characters in a string:
  - Similar to "ignore diacritics" options for pattern matching in Opus.
  - Takes a string and returns a new version of the string.
  - Example (JScript):\<WRAP\>

    function OnClick(clickData)
    {
        var st = DOpus.Create.StringTools();
        for (var eSel = new Enumerator(clickData.func.sourcetab.files); !eSel.atEnd(); eSel.moveNext())
        {
            var conv = st.RemoveDiacritics(eSel.item().Name);
            DOpus.Output('"' + eSel.item().Name + '" -> "' + conv + '"');
        }
    }

\</WRAP\>

- StringTools.Truncate -- Method. Truncates a string or path to a specified width.
- QuickFilter.flatview -- Property. Tells you if filtering of Flat View folders is on or off.
  - The old QuickFilter.overrideflatview property remains for compatibility, but is probably not very useful. It only tells you if the global Preferences setting is being overridden, but not what the Preferences setting, or the end result, actually is.
  - The new property gives you the end result directly.
- File lists passed to Command.AddFiles, Command.SetFiles, DOpus.SetClip and Dialog.Drag can now be contained in a StringSet or UnorderedSet of full path strings.
- FSUtil.Hash now supports "blake3" as a hash method.
- Scripting clickData.func.sourcetab.lister.utilpage -- Now returns "ScriptLog" for the Script Log.
- In JScript (but not VBScript), collections can now be indexed with square brackets as well as parentheses. E.g. DOpus.Listers\[0\].activetab works like DOpus.Listers(0).activetab.
- GetNewNameData.tab provides Rename scripts with the tab (and thus Lister) which launched the Rename command. Returns false if there is no tab.
- When a tab becomes active because another tab closed, the OnActivateTab method is now fired synchronously so the "oldtab" value remains valid.
- Added ActivateTabData.closing property which is True if the activation change is due to the old tab closing.
- Scripts can now extract icons from DLLs and EXEs using the standard LoadImage functions.
- Scripts can now access internal icon images. Pass the icon name prefixed with \# (e.g. "#copy"). By default, the large size is returned; use "#0:name" for the small size. You can also specify a particular set using "#set:icon" or "#0:set:icon".
- DOpus.GetClipFormat can now be asked to differentiate between files placed on the clipboard via copy and those placed via cut.
- FSUtil: Exists, GetType and PathType methods no longer trigger password prompts if given a path involving an encrypted archive.

------------------------------------------------------------------------

Next: [removed](/Manual/release_history/opus13_detailed/removed.md)
