# Sharing functions with others

Opus makes it easy to share buttons and toolbars with your friends and other Opus users. For example, you might have developed a drop-down menu containing lots of useful rename commands - if you want to share this with someone, the easiest way is to use the clipboard.

In [Customize](/Manual/customize/RAEDME.md) mode, right-click on the button or the menu that you want to share, and choose **Copy** from the context menu.

![](/Manual/images/media/share_buttons_1.png) 

At this point, you can exit Customize mode. The button or menu you copied remains on the clipboard, and you now need to get it into a form that you can give to someone else. There are two easy ways to do this:

- Use a text editor, like Notepad, to paste the clipboard contents into a new document (or, say, into an email that you're writing to someone)
- Paste the clipboard contents directly into a Lister (**Edit / Paste**) to create a new text file

Either way, this will convert the definition of the button into a text-based XML format that can be easily shared with someone.

![](/Manual/images/media/share_buttons_2.png) 

When your friend gets the text-based button code, all they have to do to add it to their own toolbar is:

- Copy the button definition to the clipboard (by selecting all the text from the *\<?xml version="1.0"?\>* line down to the final *\</button\>* line and copying it to the clipboard).
- Set Opus into [Customize](/Manual/customize/RAEDME.md) mode.
- Paste the new button to their toolbar (right-click on the toolbar and choose **Paste** from the context menu - see [Editing the Toolbar]() for more information).

You can copy an individual button, or a whole menu including all its child buttons (and any child menus it may have as well). You will often find people sharing toolbars and buttons on the Opus Resource Centre - see the [Buttons & Scripts](https://resource.dopus.com/c/buttons-scripts) forum for lots of examples!
