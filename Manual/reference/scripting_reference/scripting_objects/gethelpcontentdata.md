# GetHelpContentData

If a script implements the **[OnGetHelpContent](../scripting_events/ongethelpcontent.md)** event, it receives a **GetHelpContentData** object when the method is called. You can use the methods of this object to add your help content to the Directory Opus F1 help system.

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddHelpImage</td><td>

\<string:name\>  
\<**[Blob](blob.md)**:image\></td><td>

*none*</td><td>

Adds a PNG or JPG image and makes it available for your help pages. You can use any name you like for your images, although they must have either a **.png** or a **.jpg** suffix. Your help content can then refer to images by name, e.g. if you add an image and call it **myimage.jpg**, your html content could show it using:  
`<img src="myimage.jpg">
` If your script is bundled as a [script package](/Manual/scripting/script_add-ins/script_package.md) you can include image files in a sub-directory of the package called **help**, and then load them easily using the **[Script](script.md).LoadHelpImage** method.
</td></tr><tr><td>
AddHelpPage</td><td>
\<string:name\>  
\<string:title\>  
\<string:body\></td><td>

*none*</td><td>

Adds a page of help content for your script to the F1 help file. You can call this method as many times as you like. If you add more than one page of help the first page will become the topic header and all subsequent pages will appear underneath it in the index.  
The **name** parameter is optional; if not supplied, a default name will be assigned automatically to each page you add. You can use the **[Script](script.md).ShowHelp** method to trigger the display of a specific page of your help by name.  
The **title** parameter specifies the page title; this is shown in the help index and should be descriptive enough that the user can recognise it as referring to your script. The body parameter specifies the actual HTML content for the help page. This should be everything you would normally find *between* the **\<body\>...\</body\>** tags of an HTML page.  
If your script is bundled as a [script package](/Manual/scripting/script_add-ins/script_package.md) you can include HTML files in a sub-directory of the package called **help**, and then load them easily using the **[Script](script.md).LoadHelpFile** method.
</td></tr></tbody>
</table>

