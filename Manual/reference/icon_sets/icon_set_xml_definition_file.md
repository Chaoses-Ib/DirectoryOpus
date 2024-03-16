# Icon Set XML Definition File

The XML file defines the icons that make up the icon set. Below is an example of an Icon Set .xml file:

  
`<?xml version="1.0"encoding="utf-8"?>
<iconset name="sample">
    <display_name>SampleI con Set</display_name>
    <copyright>(c)2007 Fred Bloggs Productions</copyright>
    <artist>Fred Bloggs</artist>
    <set size="small" width="20" height="20" filename="MyIconsSmall.png">
        <icon name="copy" row="1" col="1" />
        <icon name="move" row="1" col="2" />
    </set>
    <set size="large" width="32" height="32" filename="MyIconsLarge.png">
        <icon name="copy" row="1" col="1" />
        <icon name="move" row="1" col="2" />
    </set>
</iconset>`

The root node of the definition file is called `iconset`. The `name` attribute given here specifies an internal name that is used for this set. This is never shown to the user, but is used internally for referencing icons the user has configured in their toolbar. It is important that you pick a unique name for your icon set – if two icon sets with the same internal name are installed, their contents will be merged together as if they were one big set.

Several values below the root node let you specify icon set metadata – **display_name** is the name of the set that is actually displayed to the user, and **copyright** and **artist** are strings that are shown in the list of Icon Sets in Preferences.

Following this, the **set** nodes are used to specify one or more icons in the set. Each icon set can contain one or two distinct groups of icons – a **small** group and a **large** group. The **size** attribute to the **set** node specifies which icon size is being defined, and the **width** and **height** attributes define the actual pixel sizes of the icons. The **filename** attribute specifies the image file that this group of icons is drawn from.

Below each **set** node are one or more **icon** nodes which define the individual icons that make up the set. Each icon must have a name specified with the **name** attribute, and its row and column within the image file given with the **row** and **col** attributes.

 
