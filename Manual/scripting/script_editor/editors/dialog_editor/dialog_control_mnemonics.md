# Dialog Control Mnemonics

A mnemonic, or keyboard accelerator, is a key that you can press (sometimes in conjunction with **Alt**) to activate a control rather than using the mouse. Mnemonics are specified by including an ampersand character (**&**) in a control’s title. For example, a button with the title **&Modify** could be activated by pushing the **M** key.

For complicated dialogs it can sometimes be hard to find unique letters in each control to use as a mnemonic. The **Check Mnemonics** command ( ![](/Manual/images/media/image106.png) ) can help in two ways.

Firstly, it will tell you if the same mnemonic has been assigned to two or more controls. If any mnemonics do clash, you will be given the option to select the controls (so you can identify and fix them manually), or to automatically fix them.

Secondly, if there aren’t any clashing mnemonics, but some controls do not have a mnemonic assigned at all, you’ll be given the option to automatically assign them. In either case, selecting the auto-assignment option will cause the dialog editor to recalculate mnemonics for the controls in question so that (as much as possible) all controls have a unique mnemonic key.

 
