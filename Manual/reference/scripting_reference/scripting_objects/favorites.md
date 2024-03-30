# Favorites

The **Favorites** object holds a collection of all the defined [favorite folders](/Manual/basic_concepts/the_lister/navigation/favorites.md). It is retrieved from the **[DOpus](dopus.md).favorites** property.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*collection:***[Favorite](favorite.md)**</td><td>

You can enumerate the **Favorites** object to retrieve individual **[Favorite](favorite.md)** objects.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method// Name//</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Add</td><td>

\<string:typeOrName\>  
\<string:path\>  
\<int:insertpos\> or  
\<object:**[Favorite](favorite.md)**\></td><td>

*object:***[Favorite](favorite.md)**  
or *object:***Favorites**</td><td>

Adds a new favorite folder to the favorites list. Note that changes you make to the list are not saved until you call the **Save** method.

This method performs three separate functions; it can add a separator, a sub-folder or a favorite folder. 

To add a separator, the parameters should be the type string **sep**, optionally followed by the insertion position (see below).

For example, `Favorites.Add("sep");`

You can also make the separator a heading (i.e. a label that appears visually different to other items) by appending the heading name to the **sep:** prefix. For example, `Favorites.Add("sep:Current Job");`

To add a folder, the first parameter should be the string **folder:** followed by the name of the folder (as a single parameter), optionally followed by the insertion position.

For example, `Favorites.Add("folder:Picture Locations");`

To add a new favorite, the first parameter can optionally be the name of the favorite, and the second parameter can be the path of the folder to add, or the name can be omitted and only the path can be provided. In either case you can optionally include the insertion position as the last parameter.

For example,

    Favorites.Add("myfave", "c:\folder\path");
    Favorites.Add("c:\folder\path");

In all three cases the new item is added to the end by default, but you can optionally specify a position to insert the item somewhere else. E.g. specifying **0** for the insertion position would add it at the top of the list. You can provide either a number or another **[Favorite](favorite.md)**object.

For example, `Favorites.Add("myfave", "c:\folder\path", 0);`

The return value is either a **[Favorite](favorite.md)**or a **Favorites** object (depending on whether you added a sub-folder or a favorite folder).
</td></tr><tr><td>
Delete</td><td>

\<object:**[Favorite](favorite.md)**\> or  
\<object:**Favorites**\></td><td>

*none*</td><td>

Deletes the specified favorite or sub-folder. Note that changes you make to the list are not saved until you call the **Save** method.
</td></tr><tr><td>
Find</td><td>

\<string:name\>  
\<int:index\></td><td>

*object:***Favorites**</td><td>

Lets you locate a sub-folder one or more levels below the current one. The **name** parameter is the name or path and name of the sub-folder to look for (e.g. "myfave", "pictures/local", etc).

The optional **index** parameter lets you handle the case when there might be more than one sub-folder with the same name. **Favorites.Find("pictures", 1);** would find the second sub-folder called "pictures" below the current level.
</td></tr><tr><td>
Save</td><td>

*none*</td><td>

*none*</td><td>

Saves any changes you've made to the favorites list. Once you call this method changes you have made will be reflected in Preferences and the favorites list in Listers. Note that you can only call this method on the main "root" **Favorites** object obtained from the **[DOpus](dopus.md).favorites** property
</td></tr><tr><td>
SetName</td><td>

\<string:name\></td><td>

*none*</td><td>

Changes the name of this sub-folder. Note that changes you make to the list are not saved until you call the **Save** method. You can only call this method on **Favorites** objects that refer to sub-folders, and not the main "root" folder.
</td></tr></tbody>
</table>

