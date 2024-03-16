# Toolbar Sets

A toolbar set is one or more toolbars that has been saved as a group. They are useful in two main ways:

- You can load and switch between saved sets using the **Settings / Toolbars** menu (or the context menu displayed when you right-click an empty space on a toolbar). This makes it easy to switch quickly from one set of toolbars to another.
- You can configure Opus to [automatically load](dynamic_toolbars.md) a saved set whenever a particular view mode is in use, or a specific folder is visited.

##### Saving a toolbar set

Toolbar sets are created using the toolbars in an existing Lister as a template. To create a new toolbar set you can either:

- Use the **Settings / Toolbars / Toolbar Sets / Save Toolbar Sets** command to save the toolbars in a Lister as a set, or
- Use the controls on the **[Toolbars / Toolbar Sets](/Manual/preferences/preferences_categories/toolbars/toolbar_sets.md)** page in Preferences.

##### Interaction with existing toolbars

When you create a toolbar set you can choose its default behavior - that is, how the set interacts with the existing toolbars in a Lister when it's loaded. The three choices are:

- **Add toolbars to existing toolbars** - any toolbars in the set that aren't already turned on are turned on when the set is loaded. Existing toolbars are unaffected.
- **Replace existing toolbars** - all currently open toolbars are closed and replaced with the toolbars in the set.
- **Toggle existing toolbars** - if all the toolbars in the set are turned on, they are removed and replaced with the toolbars from the default set. Otherwise, any toolbars in the set that aren't currently on are turned on. This option lets you quickly toggle between the default set and another toolbar set.

When the set is loaded the default behavior will be used unless overridden using the arguments to the internal \<ib:inline-code\>`Toolbar`\</ib:inline-code\> command. You can change the default behavior of an existing set on the **[Toolbars / Toolbar Sets](/Manual/preferences/preferences_categories/toolbars/toolbar_sets.md)** page in Preferences.

##### Default toolbar set

The *default toolbar set*, which determines a Lister's initial set of toolbars when it opens (unless overridden by a saved Lister Layout), isn't saved as a normal set. Instead, use the **Settings / Toolbars / Set As Default Toolbar Set** command to update your default toolbar set if you want to change which toolbars are used by default.
