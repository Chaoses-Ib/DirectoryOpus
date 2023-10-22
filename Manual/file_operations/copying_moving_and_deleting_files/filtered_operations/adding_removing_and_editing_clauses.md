# Adding, Removing and Editing Clauses

Each clause in the filter control has a number of controls that are used to edit the filter.

![](/Manual/images/media/filter_controls.png)

From left to right:

- The ![](/Manual/images/media/filter_-_plus.png) button adds a new clause to the filter *above* the line clicked on (to add a clause to the end of the filter, click the ![](/Manual/images/media/filter_-_plus.png) button displayed at the bottom on a line by itself).
- The ![](/Manual/images/media/filter_-_minus.png) button deletes a clause.
- The ![](/Manual/images/media/filter_-_checkbox.png) button lets you disable a clause while preserving its information (as opposed to deleting it). When a clause is disabled it has no effect on the filter at all.
- The ![](/Manual/images/media/filter_-_or.png) drop-down lets you choose the Boolean operator (**and** or **or**) linking the selected clause with the one *above* it. The very first clause in the filter, or the first clause in a sub-clause, will not have this drop-down because there is nothing to link it with.
- The ![](/Manual/images/media/filter_-_type.png) drop-down defines the [type of the clause](filter_clause_types.md) - which attribute of the file is actually compared (name, size, date, etc). This is also used to begin a new sub-clause by selecting *Subclause* from the drop-down list.
- The ![](/Manual/images/media/filter_-_match.png) drop-down lets you choose whether the clause must be **true** (*Match*) or **false** (No Match) for the filter (or parent clause) to match.

You can also edit the filter using the keyboard. Use the **Tab** key to move between controls in the current clause, and the **Up** and **Down Cursor** keys to move between clauses. You can press the **+** or **Insert** keys to add a clause, the **-** or **Delete** keys to delete a clause, and the **Space** bar to turn a clause on or off.
