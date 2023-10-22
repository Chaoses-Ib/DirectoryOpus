##### Directory Opus 13 - Detailed release notes

# Everything (indexed search)

- Integrated support for Voidtools Everything, a tool that enables instant searches of local drives.
- Within Opus, Everything can be used for searching in different ways via the search field, Find-As-You-Type (FAYT), and Tools \> Find Files. (Discussed in more detail in their respective sections.)
- Everything can also be used for instant folder size calculation. (See [Folder Sizes](folder_sizes.md) section.)
- Everything can also speed up calculation of total counts/sizes in progress dialogs.
- You can [download Everything](https://www.voidtools.com/downloads/) from the Voidtools website.
- Why Everything?:
  - It's a great tool that works well without getting in the way.
  - It's free. (You can [donate](https://www.voidtools.com/donate/) if you find it useful.)
  - It has an API designed to allow integration with other software.
  - Many Opus users already use Everything. Threads about integrating the two are some of the most popular on our forum.
  - We can improve and streamline the integration, and extend what it does beyond what's possible with user-made buttons and scripts.
  - Indexed search has memory overhead. By hooking Opus into Everything's database, rather than making our own clone, there's no extra memory overhead for people already using Everything.

- Everything is not *required* and you don't have to install it. Opus's own Find Files functionality remains, and Windows Search is still supported in various places.

------------------------------------------------------------------------

Next: [evaluator](/Manual/release_history/opus13_detailed/evaluator.md)
