# Navigation Lock

Navigation Lock (*NavLock*) is a mode you can turn on in a dual-display Lister. You can turn NavLock on using the ![](/Manual/images/media/13/navlock_button.png) button on the default toolbar.

When a Lister enters NavLock mode, Opus records the two folders that are currently displayed in both file displays. From this point on, any navigation you perform in one file display will be automatically replicated, if possible, on the other side. This mode is most useful when you have the same (or a similar) directory structure on two different drives (or on a local drive and an FTP site, for example).

##### Going out of sync

If there's no matching folder on the other side, and the action **can't** be repeated, the file displays will get out of sync. In this event, the following message will be displayed:

![](/Manual/images/media/13/navlock4.png) 

At this point you have four options:

- You can ignore the message (and dismiss it by clicking the close button).
- You can manually navigate back to an in-sync location.
- You can **reset the sync position** - this will bring the folders back into sync, and NavLock mode will remain enabled, with the current locations set as the new base folders.
- You can **turn off Navigation Lock** - either using the link in the message or by clicking the ![](/Manual/images/media/13/navlock_button.png) button again.

##### NavLock and folder tabs

Navigation Lock is a mode which applies to the Lister as a whole and not specifically to the pair of folder tabs which were active when the mode was turned on.

If you switch between different folder tabs while Navigation Lock is turned on, the Navigation Lock base folders will be reset each time. Effectively, if Navigation Lock is on when you switch to another folder tab, it is momentarily switched off and then back on again.

If you are considering using Navigation Lock in a Lister with multiple tabs, you may wish to use [linked tabs](../tabs/linked_tabs.md) instead. Linked tabs are two tabs that have been linked together, so that when one tab is activated its partner also comes to the front. Linked tabs can also be put into a version of Navigation Lock that applies only to those tabs.
