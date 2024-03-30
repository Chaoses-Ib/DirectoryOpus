# Codes for file and folder counts

The following status bar codes are used to display information about the number and size of files and folders (selected, hidden and total) in the Lister. Each code has several different forms - in a dual-display Lister this can be used to control which file display the information refers to.

<table>
<thead><tr><th>
Description</th><th>
Code</th><th>
Details
</th></tr></thead><tbody><tr><td>

**Number of selected folders**  
Displays the number of selected folders.</td><td>

{sd}  
{sdD}  
{sdL}  
{sdR}</td><td>

Selected folders in the source file display  
- destination file display  
- left/top file display  
- right/bottom file display
</td></tr><tr><td>

**Number of selected files**  
Displays the number of selected files.</td><td>

{sf}  
{sfD}  
{sfL}  
{sfR}</td><td>

Selected files in the source file display  
- destination file display  
- left/top file display  
- right/bottom file display
</td></tr><tr><td>

**Number of selected items**  
Displays the total number of selected files and folders.</td><td>

{si}  
{siD}  
{siL}  
{siR}</td><td>

Selected items in the source file display  
- destination file display  
- left/top file display  
- right/bottom file display
</td></tr><tr><td>

**Size of all selected items**  
Displays the total size of all selected files (and folders, if their size has been [calculated](/Manual/basic_concepts/folder_sizes.md)).

The size can be displayed in either bytes, or an automatic mode where the unit (bytes, KB, MB or GB) is automatically chosen depending on the size.</td><td>

{sb}  
{sbDb}  
{sbLb}  
{sbRb}  
{sba}  
{sbDa}  
{sbLa}  
{sbRa}</td><td>

Size of selected items in the source file display (in bytes)  
- destination file display (bytes)  
- left/top file display (bytes)  
- right/bottom file display (bytes)  
Size of selected items in the source file display (automatic units)  
- destination file display (automatic units)  
- left/top file display (automatic units)  
- right/bottom file display (automatic units)
</td></tr><tr><td>

**Size of all selected files**  
Displays the total size of all selected files (does not include selected folders).</td><td>

{sbf}  
{sbfDb}  
{sbfLb}  
{sbfRb}  
{sbfa}  
{sbfDa}  
{sbfLa}  
{sbfRa}</td><td>

Size of selected files in the source file display (in bytes)  
- destination file display (bytes)  
- left/top file display (bytes)  
- right/bottom file display (bytes)  
Size of selected files in the source file display (automatic units)  
- destination file display (automatic units)  
- left/top file display (automatic units)  
- right/bottom file display (automatic units)
</td></tr><tr><td>

**Size of all selected folders**  
Displays the total size of all selected folders (does not include selected files). A folder's size must have been previously [calculated](/Manual/basic_concepts/folder_sizes.md) for it to be included in this total.</td><td>

{sbd}  
{sbdDb}  
{sbdLb}  
{sbdRb}  
{sbda}  
{sbdDa}  
{sbdLa}  
{sbdRa}</td><td>

Size of selected folders in the source file display (in bytes)  
- destination file display (bytes)  
- left/top file display (bytes)  
- right/bottom file display bytes)  
Size of selected folders in the source file display (automatic units)  
- destination file display (automatic units)  
- left/top file display (automatic units)  
- right/bottom file display (automatic units)
</td></tr><tr><td>
</td><td>
</td><td>

</td></tr><tr><td>

**Total number of folders**  
Displays the total number of folders.</td><td>

{td}  
{tdD}  
{tdL}  
{tdR}</td><td>

Total folders in the source file display  
- destination file display  
- left/top file display  
- right/bottom file display
</td></tr><tr><td>

**Total number of files**  
Displays the total number of files.</td><td>

{tf}  
{tfD}  
{tfL}  
{tfR}</td><td>

Total files in the source file display  
- destination file display  
- left/top file display  
- right/bottom file display
</td></tr><tr><td>

**Total number of items**  
Displays the total number of files and folders.</td><td>

{ti}  
{tiD}  
{tiL}  
{tiR}</td><td>

Total items in the source file display  
- destination file display  
- left/top file display  
- right/bottom file display
</td></tr><tr><td>

**Size of all items**  
Displays the total size of all files (and folders, if their size has been [calculated](/Manual/basic_concepts/folder_sizes.md)).

The size can be displayed in either bytes, or an automatic mode where the unit (bytes, KB, MB or GB) is automatically chosen depending on the size.</td><td>

{tb}  
{tbDb}  
{tbLb}  
{tbRb}  
{tba}  
{tbDa}  
{tbLa}  
{tbRa}</td><td>

Size of items in the source file display (in bytes)  
- destination file display (bytes)  
- left/top file display (bytes)  
- right/bottom file display (bytes)  
Size of items in the source file display (automatic units)  
- destination file display (automatic units)  
- left/top file display (automatic units)  
- right/bottom file display (automatic units)
</td></tr><tr><td>

**Size of all files**  
Displays the total size of all files (does not include folders).</td><td>

{tbf}  
{tbfDb}  
{tbfLb}  
{tbfRb}  
{tbfa}  
{tbfDa}  
{tbfLa}  
{tbfRa}</td><td>

Size of files in the source file display (in bytes)  
- destination file display (bytes)  
- left/top file display (bytes)  
- right/bottom file display (bytes)  
Size of files in the source file display (automatic units)  
- destination file display (automatic units)  
- left/top file display (automatic units)  
- right/bottom file display (automatic units)
</td></tr><tr><td>

**Size of all folders**  
Displays the total size of all folders (does not include files). A folder's size must have been previously [calculated](/Manual/basic_concepts/folder_sizes.md) for it to be included in this total.</td><td>

{tbd}  
{tbdDb}  
{tbdLb}  
{tbdRb}  
{tbda}  
{tbdDa}  
{tbdLa}  
{tbdRa}</td><td>

Size of folders in the source file display (in bytes)  
- destination file display (bytes)  
- left/top file display (bytes)  
- right/bottom file display bytes)  
Size of folders in the source file display (automatic units)  
- destination file display (automatic units)  
- left/top file display (automatic units)  
- right/bottom file display (automatic units)
</td></tr><tr><td>

**Number of hidden folders**  
Displays the number of folders that have been hidden from the file display via the various [filters](/Manual/basic_concepts/searching_and_filtering/README.md).</td><td>

{hd}  
{hdD}  
{hdL}  
{hdR}</td><td>

Hidden folders in the source file display  
- destination file display  
- left/top file display  
- right/bottom file display
</td></tr><tr><td>

**Number of hidden files**  
Displays the number of hidden files.</td><td>

{hf}  
{hfD}  
{hfL}  
{hfR}</td><td>

Hidden files in the source file display  
- destination file display  
- left/top file display  
- right/bottom file display
</td></tr><tr><td>

**Number of hidden items**  
Displays the total number of hidden files and folders.</td><td>

{hi}  
{hiD}  
{hiL}  
{hiR}</td><td>

Hidden items in the source file display  
- destination file display  
- left/top file display  
- right/bottom file display
</td></tr><tr><td>

**Size of hidden items**  
Displays the total size of all hidden files (and folders, if their size has been [calculated](/Manual/basic_concepts/folder_sizes.md)).

The size can be displayed in either bytes, or an automatic mode where the unit (bytes, KB, MB or GB) is automatically chosen depending on the size.</td><td>

{hb}  
{hbDb}  
{hbLb}  
{hbRb}  
{hba}  
{hbDa}  
{hbLa}  
{hbRa}</td><td>

Size of hidden items in the source file display (in bytes)  
- destination file display (bytes)  
- left/top file display (bytes)  
- right/bottom file display (bytes)  
Size of hidden items in the source file display (automatic units)  
- destination file display (automatic units)  
- left/top file display (automatic units)  
- right/bottom file display (automatic units)
</td></tr><tr><td>

**Size of hidden files**  
Displays the total size of all hidden files (does not include folders).</td><td>

{hbf}  
{hbfDb}  
{hbfLb}  
{hbfRb}  
{hbfa}  
{hbfDa}  
{hbfLa}  
{hbfRa}</td><td>

Size of hidden files in the source file display (in bytes)  
- destination file display (bytes)  
- left/top file display (bytes)  
- right/bottom file display (bytes)  
Size of hidden files in the source file display (automatic units)  
- destination file display (automatic units)  
- left/top file display (automatic units)  
- right/bottom file display (automatic units)
</td></tr><tr><td>

**Size of hidden folders**  
Displays the total size of all hidden folders (does not include files). A folder's size must have been previously [calculated](/Manual/basic_concepts/folder_sizes.md) for it to be included in this total.</td><td>

{hbd}  
{hbdDb}  
{hbdLb}  
{hbdRb}  
{hbda}  
{hbdDa}  
{hbdLa}  
{hbdRa}</td><td>

Size of hidden folders in the source file display (in bytes)  
- destination file display (bytes)  
- left/top file display (bytes)  
- right/bottom file display bytes)  
Size of hidden folders in the source file display (automatic units)  
- destination file display (automatic units)  
- left/top file display (automatic units)  
- right/bottom file display (automatic units)
</td></tr><tr><td>
</td><td>
</td><td>

</td></tr><tr><td>

**Show Everything mode**  
Indicates if *[Show Everything](/Manual/basic_concepts/searching_and_filtering/show_everything.md)* mode is active.</td><td>
{hse}</td><td>

"Everything" if *Show Everything* mode is active.  
"Filtering" if *Show Everything* mode is turned off.
</td></tr><tr><td>

**Number of file groups**  
If the file display is set to group by a column this code returns the number of distinct file groups.</td><td>

{grp}  
{grpD}  
{grpL}  
{grpR}</td><td>

Number of file groups in the source file display  
- destination file display  
- left/top file display  
- right/bottom file display
</td></tr></tbody>
</table>

