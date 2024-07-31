# Responding to Events

[Script add-ins](../script_add-ins/README.md) are invoked in response to one or more [events](/Manual/reference/scripting_reference/scripting_events/README.md).

This is an example of a script add-in that responds to two different events. You would use this by creating a new **.vbs** file in the *Script Addins* folder (type **/dopusdata/Script Addins** into the location field to find this).

This example responds to both folder change (**[OnAfterFolderChange](/Manual/reference/scripting_reference/scripting_events/onafterfolderchange.md)**) and view mode change (**[OnDisplayModeChange](/Manual/reference/scripting_reference/scripting_events/ondisplaymodechange.md)**) events.

In both cases, it checks if the current folder is the *Pictures* library (**lib://Pictures** or a child folder). If so, it automatically changes the sort mode based on the current view mode:

- If the display is set to *Thumbnails* mode, the list will be sorted by date
- Otherwise, the list will be sorted by name

    ' Set the script type to VBScript to use this script.
    ' The OnInit event is called by Directory Opus to initialize the script.
    Function OnInit(ByRef initData)
        ' Provide basic information about the script.
        initData.name = "Example Event Script"
        initData.desc = "Script that shows an example of responding to events"
        initData.copyright = "(c) 2016 Jonathan Potter"
        initData.default_enable = True
    End Function

    ' The OnAfterFolderChange event is called after a folder has been read
    Function OnAfterFolderChange(ByRef afterFolderChangeData)
        ' The result property of the AfterFolderChangeData object tells us if the read was successful.
        If afterFolderChangeData.result Then
            ' Check if the path that was read begins with lib://Pictures
            If Left(afterFolderChangeData.tab.path, 14) = "lib://Pictures" Then
                ' The path matched, so call our CheckPictureSorting subroutine to update the sort mode if needed.
                ' We pass the Tab that the folder was read in as a parameter to the subroutine.
                Call CheckPictureSorting(afterFolderChangeData.tab)
            End If
        End If
    End Function

    ' The OnDisplayModeChange event is called whenever the view mode is changed.
    Function OnDisplayModeChange(ByRef displayModeChangeData)
        ' The DisplayModeChangeData object gives us the Tab that the mode was changed in.
        ' See if the folder currently displayed in the tab is lib://Pictures or a sub-folder.
        If Left(displayModeChangeData.tab.path, 14) = "lib://Pictures" Then
            Call CheckPictureSorting(displayModeChangeData.tab)
        End If
    End Function

    ' This is a subroutine called by both the above events, and is passed a Tab object as a parameter.
    ' It creates a Command object and uses the IsSet method to see if the current view mode in the tab is Thumbnails.
    ' - If so, it uses the RunCommand method to sets the sort order to "modified date".
    ' - If not, it sets the sort order to "name".
    Sub CheckPictureSorting(ByRef objTab)
        Set objCmd = DOpus.CreateCommand
        objCmd.SetSourceTab(objTab)
        If objCmd.IsSet("VIEW=Thumbnails") Then
            objCmd.RunCommand("Set SORTBY=modified")
        Else
            objCmd.RunCommand("Set SORTBY=name")
        End If
        Set objCmd = Nothing
    End Sub

  
