# Rename Scripts

This is by far the most powerful, but also most complicated, feature of the *[Advanced Rename](/Manual/file_operations/renaming_files/advanced_rename/README.md)* dialog. You can write a rename script that gives you complete control over the outcome of the rename operation.

![](/Manual/images/media/rename_scripts.png)

Here's a reasonably simple example of a scripted rename. You can see that the script editor has been shown. This is initially pre-populated with a do-nothing script that you can edit.

The *Script Type* drop-down at the top is used to specify the scripting language - in the above example, *VBScript* is selected.

1.  For each file to be renamed, Opus calls the **[OnGetNewName](/Manual/reference/scripting_reference/scripting_events/ongetnewname.md)** function.
2.  The parameter passed to the **[OnGetNewName](/Manual/reference/scripting_reference/scripting_events/ongetnewname.md)** function is a **[GetNewNameData](/Manual/reference/scripting_reference/scripting_objects/getnewnamedata.md)** object.
3.  From this we obtain the **item** property, which returns an **[Item](/Manual/reference/scripting_reference/scripting_objects/item.md)** object.
4.  From the Item object we obtain the **metadata** property, which returns a **[Metadata](/Manual/reference/scripting_reference/scripting_objects/metadata.md)** object.
5.  We check the default value of this object - if it returns *"image"* we know the item is an image file.
6.  We build a new name consisting of the original file's name stem (the **Item.name_stem** property, converted to lowercase by the VBScript **LCase** function).
7.  We then append a string displaying image's dimensions (extracted from the **Meta.image** object which provides the **picwidth** and **picheight** properties).
8.  Finally the original filename extension (**Item.ext**) is appended.
9.  The new name is returned from the **[OnGetNewName](/Manual/reference/scripting_reference/scripting_events/ongetnewname.md)** function (the convention in VBScript, shown above, is to return a value by assigning it to the name of the function itself).
10. If the image wasn't an image file we return **True** which tells Opus to skip over that file without renaming it.

Any error messages or other text output from a script can be viewed in the *Other Logs* log window, which is accessed from the [Utility Panel](/Manual/basic_concepts/the_lister/utility_panel.md) (or the **Logs / Other Logs** command in the **Help** menu). If you find a script isn't behaving as expected, you should check this log to see if any error messages are being generated. You can also output your own text to this log using the **DOpus.Output** script method, which can help with debugging.

The default configuration provides a *Number Files* script as one of the default Rename presets, which is implemented using VBScript, so please feel free to examine this for a more complex example. Finally, please see the [Rename Scripting section on the Opus Resource Centre](https://resource.dopus.com/c/rename?u=chaoses-ib) for example rename scripts you can download and use, and feel free to ask on the forum for help with writing rename scripts.

Opus also supports two alternative functions, for legacy reasons (so that scripts written for earlier versions of Opus will still work). We recommend all new scripts use the **OnGetNewName** event as shown above.

The original function supported was **Rename_GetNewName**, which takes multiple arguments providing basic information about the file to be renamed:

    Function Rename_GetNewName ( strFileName, strFilePath, 
     fIsFolder, strOldName, ByRef strNewName 
     )
    Rename_strNewName = 
     LCase(strNewName)
    End Function

The new name is returned in the "by-reference" variable **strNewName**. The second alternative function, **Rename_GetNewName2**,  is provided for scripting languages that don't support "by-reference" variables. The only difference is that **strNewName** is not passed by-reference, and you use the return value of the function to specify the new name. The above example using **Rename_GetNewName2** would look something like this:

    Function Rename_GetNewName2 ( strFileName, strFilePath, 
     fIsFolder, strOldName, strNewName 
     )
    Rename_GetNewName2 = 
     LCase(strNewName)
    End Function

More:

[Custom Fields in the Rename Dialog](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.md)  
