# Interacting with Dialog Controls

When a dialog is [detached](the_dialog_message_loop/detached_dialogs.md) (by setting the **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md).detach** property to **True**) it becomes possible for your script to interact with the controls on the dialog to a much greater extent. You can read their values at any time, not just after the dialog has closed, and you can also modify their values (both after the dialog has been created and in response to control input). The various methods and properties of the **[Control](/Manual/reference/scripting_reference/scripting_objects/control.md)** object let you read and modify control values while a detached dialog is open.

The following (admittedly artificial!) example demonstrates the script interacting with the controls on a detached dialog.

![](/Manual/images/media/image137.png)

Clicking one of the five radio buttons performs the following actions:

- The matching static text (*Option one*, etc.) will be enabled.

- The static texts corresponding to the other radio buttons will be disabled.

- The number field in the bottom-right corner will update to reflect the selected radio button.

- The static text at the bottom of the dialog will also update to reflect the selection.

Additionally, you can edit the number field in the bottom-right which will cause the appropriate radio button to be selected.

# Interacting with Dialog Controls

    Function OnClick(ByRef clickData)
      Set Dlg = DOpus.Dlg
      Dlg.window = clickData.func.sourcetab
      Dlg.template = "testdlg"
      Dlg.detach = True
      Dlg.Show

      ' Message loop.
      Do

        Set Msg = Dlg.GetMsg()

        If Msg.event = "click" And Left(Msg.control, 5) = "radio" Then

          ' Click message from one of the radio buttons.
          Call RadioSelected(Dlg, Msg)

        ElseIf Msg.event = "editchange" and Msg.control = "val" Then

          ' EditChange message from the "val" number input.
          Call EditChanged(Dlg, Msg)

        End If

      Loop While Msg

    End Function

    Sub RadioSelected(ByRef Dlg, ByRef Msg)

      If Msg.data Then ' checked?

        ' Loop through the radio controls.
        ' They're called "radio1" through "radio5".
        ' The static controls are named similarly.
        For i = 1 to 5 

          ' Was this radio button clicked?
          If Msg.control = "radio" & i Then 

            ' Enable the radio's matching static control.
            Dlg.Control("static" & i).enabled = True 

            ' Update the text in the static at the bottom of the dialog.
            Dlg.Control("seltext").label = "You selected option #" & i

            ' If (and ONLY if) we had focus, update the number field.
            ' The focus test is important because it means this event came
            ' from an actual click rather than from us calling SetCheck below.
            If Msg.focus Then Dlg.Control("val").value = i 

          Else

            ' This wasn't the clicked radio, so disable its matching static control.
            Dlg.Control("static" & i).enabled = False

          End If

        Next

      End If

    End Sub

    Sub EditChanged(ByRef Dlg, ByRef Msg) 

      ' We only want to process this when the control has focus, as
      ' otherwise the change is one we made ourselves rather than the user.

      If Msg.focus and Msg.value >= 1 and Msg.Value <= 5 Then 

        ' Check the appropriate radio button.
        Dlg.Control("radio" & Msg.Value).value = True

      End If

    End Sub

# Interacting with Dialog Controls

    <resources>
      <resource name="testdlg" type="dialog">
        <dialog fontsize="8" height="105" lang="english" title="Test!" width="180">
          <control height="10" name="radio1" title="One" type="radio" width="25" x="7" y="7" />
          <control height="10" name="radio2" title="Two" type="radio" width="25" x="7" y="19" />
          <control height="10" name="radio3" title="Three" type="radio" width="30" x="7" y="31" />
          <control height="10" name="radio4" title="Four" type="radio" width="27" x="7" y="43" />
          <control height="10" name="radio5" title="Five" type="radio" width="26" x="7" y="56" />
          <control halign="left" height="8" name="static1" title="Option one"
                   type="static" width="35" x="54" y="8" enable="no" />
          <control halign="left" height="8" name="static2" title="Option two"
                   type="static" width="35" x="54" y="20" enable="no" />
          <control halign="left" height="8" name="static3" title="Option three"
                   type="static" width="40" x="54" y="32" enable="no" />
          <control halign="left" height="8" name="static4" title="Option four"
                   type="static" width="36" x="54" y="44" enable="no" />
          <control halign="left" height="8" name="static5" title="Option five"
                   type="static" width="34" x="54" y="57" enable="no" />
          <control halign="left" height="8" name="seltext"
                   type="static" width="155" x="11" y="89" />
          <control halign="center" height="12" name="val" number="yes"
                   type="edit" updown="yes" val_max="5" val_min="1" width="39" x="130" y="70" />
        </dialog>
      </resource>
    </resources>
