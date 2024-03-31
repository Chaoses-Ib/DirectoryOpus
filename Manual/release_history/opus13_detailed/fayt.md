### Directory Opus 13 - Detailed release notes

# Find As You Type (FAYT)

- New modes:
  - For a list of default keys, see Preferences / Filtering and Sorting / Quick Keys.
  - Opus search -- Uses Opus's built-in Find Files functionality to search below the current folder:
    - If a plain string or a wildcard is entered, it will be treated as a wildcard name match.
    - If a string beginning with `=` is entered, it'll be processed by the Evaluator and can perform more complex queries (e.g. `=size>100kb`).
  - Everything (Local) -- Uses Voidtools Everything for an indexed search below the current folder.
  - Everything (Global) -- Everything indexed search of the whole machine.
  - Folders -- Shows a popup list of folders drawn from various sources (e.g. recent, favorites and aliases). You choose sources under Preferences / Filtering and Sorting / Find-As-You-Type / Folders Mode.
- Command mode:
  - Suggested completions appear as you type commands and arguments, similar to the full command editor.
  - Push <kbd>Ctrl+Space</kbd> to force suggestions to appear for the word under the cursor.
- Find mode:
  - (Configured via Preferences / Filtering and Sorting / Find-As-You-Type / Find Mode.)
  - When using the basic FAYT Find mode, the positions of matching filenames are now indicated by marks on the scrollbar, so you can tell if there are more results out of view.
  - After typing a string, you can now push <kbd>Ctrl+S</kbd> to select all matching files.
  - New option, "Keep highlights visible after field closes (<kbd>Esc</kbd> to clear)":
    - When on, matching highlights remain visible even after the FAYT field closes.
    - While highlights remain visible, <kbd>F3</kbd> and <kbd>Shift+F3</kbd> will jump to the next/previous match, overriding any normal hotkeys on them.
    - Push the Esc key to clears highlights and return to normal.
  - When highlights are *not* displayed, <kbd>Shift+F3</kbd> now repeats the last Find, searching for matches again in the current folder, using the same string as last time.
    - If repeating in the same folder, focus will be given to the last file that matched.
    - Hotkey can be changed via Customize.
    - *Command:* `CLI QUICKFINDREPEAT` is what Shift+F3 runs by default. You can also use `QUICKFINDREPEAT=next` and `QUICKFINDREPEAT=prev` to give focus to the next or previous match instead.
  - Promoted the old "fayt_firstchar_repeat" Advanced option to a checkbox on the Find Mode page.
- Search engines:
  - Options for how FAYT uses different search engines (Opus, Windows, Everything) can now be set via Preferences, on the Quick Keys page.
- FAYT Scripts:
  - Script add-ins can now extend FAYT with new modes.
  - Examples include being able to push a key, then type a string, to search for matches below a specified set of folders, regardless of starting point. We'll post some examples on the support forum.
  - Scripts are given the search string and can then do whatever they want with it, including passing it to internal commands or external tools.
  - Scripts can react as you type, or with a small delay, or when you push return. Which makes sense depends on how expensive the query is to run.
  - Similar to some of the built-in FAYT modes, scripts can feed results back to Opus which are shown in a pop-up list that's narrowed down as you type more.
  - FAYT Scripts can have settings you toggle on/off, similar to built-in modes, with a `Script.UpdateFAYTFlags()` method to update them.
- Commands:
  - Search engine can be specified when triggering a quick search via commands. E.g. `CLI QUICKSEARCH global:kittens QUICKSEARCHENGINE=everything`
  - `CLI QUICKFOLDERS=Cat` will open FAYT in Folders mode, showing a list of folders starting with "Cat".

------------------------------------------------------------------------

Next: [Search Field](/Manual/release_history/opus13_detailed/search_field.md)
