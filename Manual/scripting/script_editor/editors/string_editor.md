# String Editor

### String resources

While script dialogs provide a multi-lingual interface in the form of [language overlays](dialog_editor/language_overlays.md), scripts can also use *string resources* which provide an easy way for a script to support multiple languages for ad-hoc strings.

As a very simple example, consider the following VBScript fragment.

    If DOpus.language = "francais" Then
      DOpus.Output "Une erreur s'est produite."
    ElseIf DOpus.language = "deutsch" Then
      DOpus.Output "Ein Fehler ist aufgetreten."
    ElseIf DOpus.language = "espanol" Then
      DOpus.Output "Ocurrió un error."
    Else
      DOpus.Output "An error occurred."
    End If

This tests the current language Opus is running in and prints an appropriate “hello” string in that language, or in English if the language isn’t known. That’s fine for a single string, but having to do that for every string in the script could be a lot of typing. Using string resources, the above script fragment reduces to:

    DOpus.Output DOpus.Strings.Get("error")

### String editor

To add a new string resource language, switch to the *Resources* tab in the script editor, right-click the script file in question, and choose **New Strings** from the context menu. Opus will prompt you to select the language you want to add strings for.

The string resource editor is a very simple grid with two columns. The *Name* column lets you specify a name for the string - in the above example, this was set to "error". The *Translation* column lets you provide the translation for the selected language.

![](/Manual/images/media/13/scripteditor_strings.png)
