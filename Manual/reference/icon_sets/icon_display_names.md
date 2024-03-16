# Icon Display Names

By default, the names given to each icon are shown to the user when they hover over each image in the *Select Icon* dialog. If desired, you can specify a “display name” for each icon, which is displayed alongside the icon’s real name.

The internal icons have automatic display names – for example, hovering over the internal Move As icon displays “Move As (moveas)” as the tooltip. “moveas” is the icon’s internal name, but “Move As” is the display name.

If your icons have the same name as the internal icons, they will be given localized display names automatically. Otherwise, you can provide display names for your icons as follows:

    <set size="small" width="20" height="20" filename="UtilIcons.png">
        <icon name="burncd" display_name="Burn To CD" row="2" col="8" category="Tools" />
    </set>
