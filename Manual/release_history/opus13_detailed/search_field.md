##### Directory Opus 13 - Detailed release notes

# Search Field

- The search field, normally at the Lister's top right, now supports multiple methods:
  - Windows Search -- As in Opus 12.
  - Everything search -- If Voidtools Everything (see [separate section](/Manual/release_history/opus13_detailed/everything.md)) is installed, you can use it for an indexed search on the current folder.
  - Global Everything search -- Similar to Everything search, but searches all indexed folders on the entire machine.
  - Opus search -- You can now use Opus's own Find Files functionality from the Search Field, without opening the larger Find panel:
    - If a plain string or a wildcard is entered, it will be treated as a wildcard name match.
    - If a string beginning with \<ib:inline-code\>`=`\</ib:inline-code\> is entered, it'll be processed by the Evaluator and can perform more complex queries (e.g. =size\>100kb).

- Click the magnifying glass icon on the left to open a menu where you can change search engine.
- The menu for changing search engines also lets you configure various options for each one (e.g. case sensitive, partial match, content searching). Each search engine has slightly different options.
- The last chosen search engine is remembered automatically.
  - You set the search field's arguments to (e.g.) \<ib:inline-code\>`everything`\</ib:inline-code\> to make it always switch to that mode in new windows.

- Search field has a history menu on the right, with a Clear History option at the bottom of the menu.
- Suggestions based on search history will appear as you type into the search field. (Add \<ib:inline-code\>`noautocomplete`\</ib:inline-code\> to the field's arguments if you don't like them appearing.)
- Commands:
  - \<ib:inline-code\>`Find`\</ib:inline-code\> and similar commands let a search engine be specified and support options as part of the command line.
  - Example, Windows search: \<ib:inline-code\>`QUERYENGINE="windows,nqs,noautowildcard,nohistory"`\</ib:inline-code\>
  - Example, Everything: \<ib:inline-code\>`QUERYENGINE="everything,case,wholeword,regex,diacritics"`\</ib:inline-code\>

------------------------------------------------------------------------

Next: [find](/Manual/release_history/opus13_detailed/find.md)
