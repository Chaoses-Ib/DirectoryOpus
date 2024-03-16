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
    - Stored queries that use Opus Find can also supply a text filter (see below) definition by prefixing it with a & character, or Evaluator code by prefixing with \<ib:inline-code\>`=`\</ib:inline-code\>.
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
  - New "Exclude" field lets you exclude files and folders. Excludes Recycle Bin and System Volume Information folders by default. Supports multiple paths, wildcards and regex. Syntax options:
    - \<ib:inline-code\>`regex:xxxx`\</ib:inline-code\> - Regular expression must match to exclude an item.
    - \<ib:inline-code\>`wild:xxxx`\</ib:inline-code\> - Standard wildcard must match to exclude an item.\<WRAP\>

(Wildcards are auto-detected without the \<ib:inline-code\>`wild:`\</ib:inline-code\> prefix if using \<ib:inline-code\>`*?|`\</ib:inline-code\> characters. Other wildcard characters which are valid path characters require an explicit \<ib:inline-code\>`wild:`\</ib:inline-code\> prefix to be interpreted as such.)\</WRAP\>

        * <ib:inline-code><code>C:\Temp</code></ib:inline-code> - Fully qualified path; matches path itself and contents.
        * <ib:inline-code><code>C:\Temp\*</code></ib:inline-code> - Fully qualified path, with wildcard; matches contents only.
        * <ib:inline-code><code>Name</code></ib:inline-code> - Non-wild, non fully qualified; matches itself and contents. Turns into: <ib:inline-code><code>*\Name(|\*)</code></ib:inline-code> 
        * <ib:inline-code><code>Name\*</code></ib:inline-code> - Non-wild name with trailing <ib:inline-code><code>*</code></ib:inline-code>; matches contents only. Turns into: <ib:inline-code><code>*\Name\*</code></ib:inline-code>
        * <ib:inline-code><code>Name*</code></ib:inline-code> - Wild name; matches itself and contents. Turns into: <ib:inline-code><code>*\Name*</code></ib:inline-code>
    * Simple mode:        
      * Size units (KB/MB/GB) can be selected.
      * Text (contents search) field has "Assume UTF8" option.
      * Enhancements to "any word" matching:              
        * Words prefixed with <ib:inline-code><code>+</code></ib:inline-code> must match (in any order).
        * Words prefixed with <ib:inline-code><code>-</code></ib:inline-code> must not match.
        * Words without <ib:inline-code><code>+</code></ib:inline-code> or <ib:inline-code><code>-</code></ib:inline-code> may match, and at least one must match if any are specified.
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
        * Prefix the filter definition with <ib:inline-code><code>=</code></ib:inline-code>.
        * If Evaluator code is in the text filter control, it can't be switched out of text mode. Evaluator code can't be converted to a traditional filter definition.
        * Code can uses the same variables (e.g. name, picwidth, etc.) as Evaluator Columns (see elsewhere in the release notes).
        * Code should return true a match, and false to skip the file.
        * //Example 1:// <ib:inline-code><code>=ext(name) == ".jpg" && picwidth >= 1920</code></ib:inline-code>
        * Can handle subfolder recursion as well. The <ib:inline-code><code>subfolder</code></ib:inline-code> variable will be true when the evaluator is querying whether a folder should be entered. Return true to enter or false to skip. By default all subfolders are searched.
        * //Example 2:// <ib:inline-code><code>=subfolder ? (left(name, 1) == "a") : (ext(name) == ".jpg")</code></ib:inline-code> -- Find JPG files under folders whose names begin with "a".
    * Commands:       
      * <ib:inline-code><code>Find FILTERDEF</code></ib:inline-code> -- Allows passing a filter definition in text form. Also allows Evaluator code. See "advanced mode", above.
      * <ib:inline-code><code>Find HERE</code></ib:inline-code> -- Specifies that the Find operation should work from the current folder.
      * <ib:inline-code><code>Find UAC=yes</code></ib:inline-code> -- Turn on searching inside folders that require elevation to look inside.
      * <ib:inline-code><code>Find PRESET="My Preset"</code></ib:inline-code> -- Runs the specified preset immediately.
      * <ib:inline-code><code>Find PRESET="My Preset" NOAUTORUN</code></ib:inline-code> -- Opens the Find panel with the preset loaded.
      * <ib:inline-code><code>Find PRESET=!list</code></ib:inline-code> -- Generates a list of Find presets. Used by the default Tools > Find Presets menu. Can also specify "faves", "nofaves" or "nogroups".
      * <ib:inline-code><code>Set Utility=Find PRESET="My Preset"</code></ib:inline-code> -- Alternative way to open the Find panel with a preset.
      * <ib:inline-code><code>Set UTILITY=Find,Toggle</code></ib:inline-code> -- Old command now toggles the Find panel regardless of its Simple or Advanced state. When re-opening, panel opens in the mode which was last closed.
      * <ib:inline-code><code>Set UTILITY=FindSimple,Toggle</code></ib:inline-code> -- Explicitly toggle the Find panel in Simple mode.
      * <ib:inline-code><code>Set UTILITY=FindAdvanced,Toggle</code></ib:inline-code> -- Explicitly toggle the Find panel in Advanced mode.
      * <ib:inline-code><code>Go NEW=FindPanel</code></ib:inline-code> -- Similarly, opens the new window's Find panel in the last used Simple or Advanced mode.
      * <ib:inline-code><code>Go NEW=FindSimple</code></ib:inline-code> -- Explicitly opens a new window with the Find panel in Simple mode.
      * <ib:inline-code><code>Go NEW=FindAdvanced</code></ib:inline-code> -- Explicitly opens a new window with the Find panel in Advanced mode.
      * <ib:inline-code><code>Find SHOWRESULTS=tab,left</code></ib:inline-code> -- Send results to new tab on the left (or right).
      * Other new Find command arguments: EXCLUDEHIDDEN, EXCLUDESYSTEM, IGNOREDIACRITICS, REGEXP, CASE, CONTREGEXP, CONTIGNOREDIACRITICS, CONTNOPARTIAL, CONTUTF8, QUERYENGINE.
      * <ib:inline-code><code>DOpusRT.exe /col /engine=everything setquery...</code></ib:inline-code> -- See //External Manipulation of File Collections// in the main manual.

------------------------------------------------------------------------

Next: [duplicates](/Manual/release_history/opus13_detailed/duplicates.md)
