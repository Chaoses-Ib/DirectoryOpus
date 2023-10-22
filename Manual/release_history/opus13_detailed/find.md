##### Directory Opus 13 - Detailed release notes

# Find Files

- General:
  - Redesigned UI.
  - Removed Simple/Advanced tab control, replacing it with "Advanced Mode" checkbox in the panel's header.
  - Replaced "Reset" button with a menu in the header.
  - You can now save your own defaults and reset to them, as well as the factory defaults.
  - Within the Exclude field, click the cog button for options to exclude hidden and system folders.
  - "Suppress UAC prompts" option: If there's an access denied error when trying to look in a file or folder, it will be skipped rather than prompting for elevation.
  - If a search finishes without finding any results, a message will say so at the top of the file display.
  - 'Ignore diacritics' options added.
  - Fields like Name, Description, Contains/Text, Tags, Target, etc. now have the full set of matching options (case / partial / any word / ignore diacritics / wildcards / regex).
  - "Indexed search" field lets you specify an indexed search query, and then feed the results through the rest of the Find parameters.
    - Lets you narrow down which files are considered, using a fast indexed search, and then apply more advanced criteria to filter them down even more.
    - Works with Windows Search, Everything, and Global Everything.
  - The "Save as Stored Query" command now works in a collection generated using the Find dialog.
    - The Find Panel's configuration will be stored as part of the collection.
    - Creates a file collection which automatically re-runs the Find each time you navigate to it, and/or on refresh.
  - Stored Queries now work with Everything and Opus Find.
    - Stored queries that use Opus Find can also supply a text filter (see below) definition by prefixing it with a & character, or Evaluator code by prefixing with \`=\`.
  - "Show Results" now lets you send results to a new tab on the left or right (not just source or destination).
  - "Automatically shrink" option can now be found by right-clicking the Utility Panel's Shrink button (next to the close button).
  - "Find Results" now has its own folder format, distinct from the more general "Collection" format.
- Presets:
  - You can now configure the Find Panel and save everything as a named preset.
  - Presets can be loaded into the Find Panel, and also used with the Find command.
  - In the lister, the default Tools menu has a Find Presets sub-menu that lists any saved presets. Selecting one immediately runs the saved search without having to open the Find Panel.
  - The Tools menu's Presets sub-menu also includes a couple of examples using hardcoded filters to search below the current directory:
    - Find Empty Folders -- Finds completely empty folders.
    - Find Zero-Byte Folders -- Finds folders which only contain empty files or other empty folders.
- Exclude folders:
  - New "Exclude" field lets you exclude files and folders. Excludes the Recycle Bin by default. Supports multiple paths, wildcards and regex. Syntax options:
    - \`regex:xxxx\` - Regular expression must match to exclude an item.
    - \`wild:xxxx\` - Standard wildcard must match to exclude an item.\<WRAP\>

(Wildcards are auto-detected without the \`wild:\` prefix if using \`\*?\|\` characters. Other wildcard characters which are valid path characters require an explicit \`wild:\` prefix to be interpreted as such.)\</WRAP\>

        * `C:\Temp` - Fully qualified path; matches path itself and contents.
        * `C:\Temp\*` - Fully qualified path, with wildcard; matches contents only.
        * `Name` - Non-wild, non fully qualified; matches itself and contents. Turns into: `*\Name(|\*)` 
        * `Name\*` - Non-wild name with trailing `*`; matches contents only. Turns into: `*\Name\*`
        * `Name*` - Wild name; matches itself and contents. Turns into: `*\Name*`
    * Simple mode:        
      * Size units (KB/MB/GB) can be selected.
      * Text (contents search) field has "Assume UTF8" option.
      * Enhancements to "any word" matching:              
        * Words prefixed with `+` must match (in any order).
        * Words prefixed with `-` must not match.
        * Words without `+` or `-` may match, and at least one must match if any are specified.
        * If one or more file extensions are specified, all folders will be excluded, and files must match one of the extensions (in addition to any other words specified).
        * Partial file extensions are supported. ".jp" will also match ".jpg".
        * Partial extension matching can be suppressed by using an explicit wildcard: "*.jp" will only match ".jp" and not ".jpg".
        * All other words containing wildcards will be treated as if partial matching is on, whether it actually is or not.                       
        * //Example:// With partial off, "dog c?t" - "dog" will only match "dog" (because no wildcard chars), but "c?t" will match both "cat" and "city".
        * Remember that the rules above only work with "any word" mode. They can't be used when the mode isn't on.
        * These rules also work in the Filter Bar when it is "any word" mode.
    * Advanced mode:      
      * Added "Name Stem" filter clause. Matches against filenames without their extensions.
      * Added "Folder Content" filter clause. Lets you search for folders containing files that match the specified criteria.
      * Filters can now be edited in text form, as well as through the GUI builder:               
        * You can switch back and forth between modes at any time (provided the text is valid).
        * Text filter definitions can be used in standalone buttons, instead of having to save the filter to the global list and refer to it by name.
        * Text filters can also be generated or modified by script code, allowing scripts to change individual parameters within a filter.
        * Text filters are also easier to share with other people (e.g. on the support forum).
      * Text filters can also run Evaluator code:                 
        * Bypasses the filter system completely and invokes the Evaluator on each file.
        * Prefix the filter definition with `=`.
        * If Evaluator code is in the text filter control, it can't be switched out of text mode. Evaluator code can't be converted to a traditional filter definition.
        * Code can uses the same variables (e.g. name, picwidth, etc.) as Evaluator Columns (see elsewhere in the release notes).
        * Code should return true a match, and false to skip the file.
        * //Example 1:// `=ext(name) == ".jpg" && picwidth >= 1920`
        * Can handle subfolder recursion as well. The `subfolder` variable will be true when the evaluator is querying whether a folder should be entered. Return true to enter or false to skip. By default all subfolders are searched.
        * //Example 2:// `=subfolder ? (left(name, 1) == "a") : (ext(name) == ".jpg")` -- Find JPG files under folders whose names begin with "a".
    * Commands:       
      * `Find FILTERDEF` -- Allows passing a filter definition in text form. Also allows Evaluator code. See "advanced mode", above.
      * `Find HERE` -- Specifies that the Find operation should work from the current folder.
      * `Find UAC=yes` -- Turn on searching inside folders that require elevation to look inside.
      * `Find PRESET="My Preset"` -- Runs the specified preset immediately.
      * `Find PRESET="My Preset" NOAUTORUN` -- Opens the Find panel with the preset loaded.
      * `Find PRESET=!list` -- Generates a list of Find presets. Used by the default Tools > Find Presets menu. Can also specify "faves", "nofaves" or "nogroups".
      * `Set Utility=Find PRESET="My Preset"` -- Alternative way to open the Find panel with a preset.
      * `Set UTILITY=Find,Toggle` -- Old command now toggles the Find panel regardless of its Simple or Advanced state. When re-opening, panel opens in the mode which was last closed.
      * `Set UTILITY=FindSimple,Toggle` -- Explicitly toggle the Find panel in Simple mode.
      * `Set UTILITY=FindAdvanced,Toggle` -- Explicitly toggle the Find panel in Advanced mode.
      * `Go NEW=FindPanel` -- Similarly, opens the new window's Find panel in the last used Simple or Advanced mode.
      * `Go NEW=FindSimple` -- Explicitly opens a new window with the Find panel in Simple mode.
      * `Go NEW=FindAdvanced` -- Explicitly opens a new window with the Find panel in Advanced mode.
      * `Find SHOWRESULTS=tab,left` -- Send results to new tab on the left (or right).
      * Other new Find command arguments: EXCLUDEHIDDEN, EXCLUDESYSTEM, IGNOREDIACRITICS, REGEXP, CASE, CONTREGEXP, CONTIGNOREDIACRITICS, CONTNOPARTIAL, CONTUTF8, QUERYENGINE.
      * `DOpusRT.exe /col /engine=everything setquery...` -- See //External Manipulation of File Collections// in the main manual.

------------------------------------------------------------------------

Next: [duplicates](/Manual/release_history/opus13_detailed/duplicates.md)
