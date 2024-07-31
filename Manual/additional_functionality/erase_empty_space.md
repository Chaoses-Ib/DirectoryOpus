# Erase Empty Space

The Erase Empty Space tool lets you securely overwrite all the empty space on a hard drive. Any data on the drive won't be affected.

![](/Manual/images/media/13/eraseemptyspace.png)

This command isn't exposed in the default toolbars, but you can easily add it yourself:

- Open the [Customize](/Manual/customize/README.md) dialog (Settings \> Customize Toolbars and Keys).
- Select the **Commands** tab
- In the **File Operations** category locate the **Secure Erase Empty Space** command
- Drag that to your toolbar or menu

The underlying raw command is `Delete ERASEEMPTYSPACE`.

### Using the tool

The tool itself is quite simple to use. A dropdown list lets you choose the drive to erase. You can set the number of passes for secure overwriting - one is usually enough, but you can increase it for greater security. Then click the **Erase** button to proceed.
