# String Resources

As well as *dialog resources*, scripts can also have *string resources* which provides an easy way for a script to support languages for ad-hoc strings (that is, for strings not part of a static dialog but used programmatically by the script). Strings defined in dialogs (e.g. *Button* control labels) can be translated using the *[Language overlays](../script_dialogs/dialog_editor/language_overlays.md)* feature.

As a very simple example, consider the following VBScript fragment.

    If DOpus.language = "francais" Then
    DOpus.Output "Bonjour!"
    ElseIf DOpus.language = "deutsch" Then
    DOpus.Output "Guten Tag!"
    Else
    DOpus.Output "Hello!"
    End If

This tests the current language Opus is running in and prints an appropriate “hello” string in that language, or in English if the language isn’t known. That’s fine for a single string, but having to do that for every string in the script could be a lot of typing. Using string resources, the above script fragment reduces to:

    DOpus.Output DOpus.Strings.Get("hello")

The actual strings themselves are provided as an XML resource, much the same way as dialog definitions are. Here’s the string resource that provides the above strings:

    <resources>
    <resource type="strings">
    <strings lang="francais">
    <string id="hello" text="Bonjour!" />
    </strings>
    <strings lang="deutsch">
    <string id="hello" text="Guten Tag!" />
    </strings>
    <strings lang="english">
    <string id="hello" text="Hello!" />
    </strings>
    </resource>
    </resources>

As you can see, there are three **strings** tags, each one with a different **lang** attribute (this specifies the language). Inside each **strings** tag are one or more **string** tags which provide the actual strings. The **id** attribute is a name of your choosing – it’s how your script refers to the string. The **text** attribute provides the translation of the string in the specified language.

The values for the **lang** attribute correspond to the names of the Directory Opus language libraries (which can be found in the **/home/Language** folder) – **english**, **deutsch**, **francais**, **cat**, **czech**, **espanol**, etc.

Note that there isn’t currently a GUI for editing string resources like there is for dialogs, so you need to code the XML resources yourself if you want to use them.

 
