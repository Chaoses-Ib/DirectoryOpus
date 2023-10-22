\<evalcmd\> LanguageStr && string && The specified translation string. && id && string && String ID to return. Currently defined strings are:

| ID            | English language string |
|---------------|-------------------------|
| FavoritesBar  | Favorites Bar           |
| CopySelection | Copy Selection          |
| CopyAll       | Copy All                |

\</evalcmd\>

This function mainly exists for the default toolbars, which in some cases need to be able to access the translation of a string in the currently selected language. You probably won't need this function yourself.

For example, in the viewer toolbar, the following line sets the button's label to either "Copy Selection" or "Copy All" (in the current language), depending on whether a region is selected or not.

    @label:LanguageStr(selimage ? "CopySelection" : "CopyAll")
