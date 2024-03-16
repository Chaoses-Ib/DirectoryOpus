# Adding, Removing and Editing Clauses

Each clause in the filter control has a number of controls that are used to edit the filter.

![](/Manual/images/media/13/filter_controls.png)

From left to right:

- The <kbd>+</kbd> button adds a new clause to the filter *above* the line clicked on (to add a clause to the end of the filter, click the <kbd>+</kbd> button displayed at the bottom on a line by itself).
- The <kbd>-</kbd> button deletes a clause.
- The checkbox lets you disable a clause while preserving its information (as opposed to deleting it). When a clause is disabled it has no effect on the filter at all.
- The drop-down labelled **And** above lets you choose the Boolean operator (**and** or **or**) linking the selected clause with the one *above* it. The very first clause in the filter, or the first clause in a sub-clause, will not have this drop-down because there is nothing to link it with.
- The drop-down labelled **Name** above selects the [type of the clause](filter_clause_types.md) - which attribute of the file is actually compared (name, size, date, etc). This is also used to begin a new sub-clause by selecting *Subclause* from the drop-down list.
- The drop-down labelled **Match** above lets you choose whether the clause must be **true** (*Match*) or **false** (No Match) for the filter (or parent clause) to match.

You can use the filter control with the keyboard:

- <kbd>Tab</kbd> to move between controls in the current clause
- <kbd>Up</kbd> and <kbd>Down</kbd> to move between clauses
- <kbd>+</kbd> or <kbd>Ins</kbd> to add a clause
- <kbd>-</kbd> or <kbd>Del</kbd> to delete a clause
- <kbd>Space</kbd> to turn a clause on or off
