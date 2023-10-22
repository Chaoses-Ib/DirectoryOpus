\<evalcmd\> IsParent && int && Number of levels difference between the paths. && parent && path && Parent path to test. && child && path && Child path to test against parent. \</evalcmd\>

Tests whether *parent* is a parent of *child*.

If not, returns \`0\`. Otherwise, returns the number of levels that *parent* is above *child*.

//<Example://>

    parentPath = "C:\Windows";
    childPath = "C:\Windows\System32";
    Output( IsParent(parentPath, childPath) );
    --> 1

*See also:*  
[count](count.md)  
[parent](parent.md)  
