# Edit Control Properties

Note that the *Edit Control* uses the **Title** property to set its default value. The specific properties applicable to the *Edit Control* are:

- **Edit Type**: Sets the type of the edit control. The available types are:
  - **Single line**: Allows the entry of a single line of text.
  - **Multiline**: Lets you enter multiple lines of text. When the cursor is on this type of control, pushing the **Return** key will insert a line break in the text.
  - **Number**: Allows the entry of a positive, whole number.
  - **Password**: Designed for password entry, this control type obscures the text you type into it.
- **Cue Text**: Specifies a “cue” string that’s displayed by the control when it’s empty (i.e. to provide a hint to the user as to what they should enter). Only available in **Single line** mode.
- **Read Only**: Set to **True** to make the control “read only” – text in it can be viewed, selected and copied, but not edited.
- **Max Length**: Sets the maximum length in characters that can be entered into the control. If empty (or set to **0**) there will be no limit on the amount of text that can be entered.
- **Up/Down Control**: Set to **True** to give a **Number** control a set of up/down arrows that the user can click to adjust the value.
- **Minimum Value**: Sets the minimum acceptable value the Up/Down control will allow the user to enter.
- **Maximum Value**: Sets the maximum acceptable value the Up/Down control will allow the user to enter.
