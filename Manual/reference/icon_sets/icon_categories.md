# Icon Categories

Directory Opus groups its internal icon set into categories to make it easier for the user to find a particular icon. The *Select Icon* dialog lets the user filter by category as well as by name. The internal icons have all been pre-assigned categories – if your icons use the same names as the internal icons then they will automatically adopt the pre-assigned categories. For example, the “copy” icon is pre-assigned to the “file” category, so if your icon set provides an icon called “copy”, the user will see it in the *Select Icon* dialog when they set the category filter to “File.”

If your icon has a name that is not in the internal icon set, it will by default be listed as Uncategorized. It is possible, but not obligatory, to specify your own categories for your icons. The default categories used by Opus are “config”, “edit”, “file”, “ftp”, “misc”, “go”, “tools”, “view” and “window.” For each icon, you can optionally specify one of the default categories, or define your own custom category. 

You can assign categories to your icons on an icon-by-icon basis, using the **icon** node, or to a number of icons at once, using the `set` node. For example,

    <set size="small" width="20" height="20" filename="UtilIcons.png">
        <icon name="burncd" row="2" col="8" category="Tools"/>
        <icon name="ftpimage" row="3" col="1" category="Image"/>
    </set>

This would define an icon called “burncd” in the “Tools” default category, and another called “ftpimage” in a custom category called “Image”.

Alternatively, both these icons could be placed in the “File” category as follows:

    <set size="small" width="20" height="20" filename="UtilIcons.png">
        <category name="File">
            <icon name="burncd" row="2" col="8" />
            <icon name="ftpimage" row="3" col="1" />
        </category>
    </set>

You must use one style or the other within a given `set`. If any `category` nodes are present then all `icon` nodes should be under a `category`. If you want to use the second style but also want some uncategorized icons, you should put them in a `category` node that does not have a `name` attribute.

Again, it is not essential to categorize your icons. If you use the default icon names they will be categorized automatically (although you can override the automatic categorization if desired), and if not they will still work, but be listed as “Uncategorized” in the *Select Icon* dialog.

  
