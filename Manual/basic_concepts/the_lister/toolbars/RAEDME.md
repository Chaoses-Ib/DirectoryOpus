# Toolbars

Toolbars are one of the main ways of interacting with Opus - they let you perform operations on files and launch programs. Some important points to note about Opus toolbars are:

- All toolbars and menus in Opus are [configurable](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/RAEDME.md) via the [Customize](/Manual/customize/RAEDME.md) function.
- In Opus, toolbars and menus are the same thing.
- Toolbar buttons can run [internal commands](/Manual/reference/command_reference/internal_commands/RAEDME.md), [scripts](/Manual/scripting/RAEDME.md) and launch [external programs](/Manual/customize/creating_your_own_buttons/passing_files_to_external_programs.md), and can pass along the names of selected files and other information automatically.
- Toolbar buttons can have associated *hotkeys* that let you launch the function from the keyboard rather than the mouse. From the Customize dialog you can elect to always enable a toolbar's hotkeys - even if the toolbar isn't current open, its hotkeys will still work.
- Toolbars can either be displayed in the Lister, or can be [floating](/Manual/additional_functionality/floating_toolbars/RAEDME.md) on the desktop, or both. You can even float multiple copies of the same toolbar if desired.
- Toolbar buttons can consist of a text label, a graphical image, or both.
- Toolbars can be set to [appear automatically](/Manual/basic_concepts/the_lister/toolbars/dynamic_toolbars.md) when changing to a certain display mode, or visiting a certain folder.
- Multiple toolbars can be saved to a [Toolbar set](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.md) which can then be reloaded later.
- Specific Listers can be saved with their own toolbars using the [Lister Layouts](layouts/RAEDME.md) system.
- The toolbars that a Lister displays by default are stored in what is known as the *Default Toolbar Set* - this is used whenever a Lister doesn't have its own set of toolbars defined in the Layout it came from. Use the **Settings / Toolbars / Set As Default Toolbar Set** command to update your default toolbar set if you want to change which toolbars are used by default.  
  \* Opus ships with five [factory-default toolbars](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/RAEDME.md) - you can edit them but you can't delete them. You can create as many other toolbars as you want.

You can turn toolbars on and off using the list in [Customize](/Manual/customize/RAEDME.md), from the **Settings / Toolbars** menu, or by right-clicking an empty space on any toolbar to bring up its context menu.

More:

[The Default Toolbars](/Manual/basic_concepts/the_lister/toolbars/the_default_toolbars/RAEDME.md)  
[Dynamic Toolbars](/Manual/basic_concepts/the_lister/toolbars/dynamic_toolbars.md)  
[Toolbar Sets](/Manual/basic_concepts/the_lister/toolbars/toolbar_sets.md)  
