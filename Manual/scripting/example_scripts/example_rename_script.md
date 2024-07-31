# Example Rename Script

This is an example of a [rename script](../rename_scripts/README.md) that adds an image file's resolution to its filename.

You would use this script through the **[Advanced Rename](/Manual/file_operations/renaming_files/advanced_rename/README.md)** dialog (turn on the **Script mode** option to display the script editor). You could also [embed the script in a button](/Manual/customize/creating_your_own_buttons/embedding_rename_scripts.md).

    ' Set the script type to VBScript to use this script
    Option Explicit

    ' Main Rename entry point.
    ' The method is passed a GetNewNameData object for each file.
    Function OnGetNewName ( ByRef GetNewNameData )
        Dim item, meta

        ' Get the provided Item object from the GetNewNameData object's item property.
        Set item = GetNewNameData.item

        ' Request its metadata. This will return a Metadataobject.
        Set meta = item.metadata

        ' If the primary type of the meta data is "image" then we know it's an image file.
        If meta = "image" Then
            ' Build and return the new name
            ' This is made up of
            ' - the "name stem" (the original filename minus the file extension)
            ' - the image width and height, obtained from the ImageMeta object (which comes from the Metadata.image property)
            ' - the original filename extension.
            OnGetNewName = item.name_stem & " (" & meta.image.picwidth & "x" & meta.image.picheight & ")" & item.ext
        Else
            ' The item wasn't an image, so return True to skip it.
            OnGetNewName = True
        End If
    End Function

  
