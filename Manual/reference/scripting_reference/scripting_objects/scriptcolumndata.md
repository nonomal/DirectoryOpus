# ScriptColumnData

The **ScriptColumnData** object is passed to the script-defined entry points for any [custom columns](/Manual/scripting/example_scripts/adding_a_new_column.md) added by a [script add-in](/Manual/scripting/script_add-ins/README.md). The method name for these events is defined by the script itself, but generically it's referred to as **[OnScriptColumn](../scripting_events/onscriptcolumn.md)**. Note that the fields **group**, **sort**, **type** and **value** are settable and are the way your method returns values for your column.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
col</td><td>

*string*</td><td>

Provides the name of the column that Opus wants the script to return the value for. If you use the same **[OnScriptColumn](../scripting_events/onscriptcolumn.md)**method to provide multiple columns you can use this to tell the columns apart.
</td></tr><tr><td>
columns</td><td>

*object:***[Map](map.md)**</td><td>

If the **[ScriptColumn](scriptcolumn.md).multicol** value is set to **True** when the column is added, then this property provides a **[Map](map.md)** that lets you return the values of one or more columns at once.

You may want to use this method if your script returns multiple columns that all share common calculations (e.g. reading the contents of a folder). That way, you can avoid repeating potentially time consuming operations when you're called for the second and subsequent columns.

The **[Map](map.md)** contains one member element for each of your columns. Each member element has **group**, **group_type**, **sort**, **type**, **userdata**, and **value** properties which are equivalent to the ones described below.

For example, you might set the value of a column called *MyColumn* like this:

*scriptColData.columns("MyColumn").value = "My Column Value";*  
You should check if a column exists in the map before populating data for it. In some situations, Opus will only request a some of the columns your add-in supports, not all of them.  
If you do not fill in data for a column which Opus still needs, Opus will call your method again to request it, with its name in the **col** property (but still in multi-column mode). You can take advantage of this if calculating one piece of data yields values for some of your columns but not all of them. You do not need to populate every column if the data is not available, but you should at least populate the **col** column.  
As a consequence of the above, when using multi-column mode you should *always* set some kind of value for any column you have spent time calculating, even if the result of the calculation is that nothing should be shown in the column. If nothing should be shown, set the value to an empty string (this is fine even if the column normally displays numbers or another type of data). If you don't set any value at all, Opus will assume you haven't calculated that column yet and may call your script again to ask for it, which could cause you to waste time re-calculating it when you already know it is blank.
</td></tr><tr><td>
group</td><td>

*string*</td><td>

If the **[ScriptColumn](scriptcolumn.md).autogroup** value is set to **False** when the column is added, you should set this value to indicate the group that this file should be placed in when the list is grouped by your column. If you don't provide a group then this file will go into the *Unspecified* group. If **autogroup** is set to **True** this value is ignored.

Note that if the **[ScriptColumn](scriptcolumn.md).multicol** value is set to **True** when the column is added then this property will be found inside the **columns** **[Map](map.md)**.
</td></tr><tr><td>
group_type</td><td>

*string*</td><td>

If the group is set via the **group** property, **group_type** lets you control the formatting of the group title using the same keywords as the **type** field (e.g. you can supply a number and have the group title formatted as a file size by setting *group_type="size"*).

Note that if the **[ScriptColumn](scriptcolumn.md).multicol** value is set to **True** when the column is added then this property will be found inside the **columns** **[Map](map.md)**.
</td></tr><tr><td>
item</td><td>

*object:***[Item](item.md)**</td><td>

Returns an **[Item](item.md)** object representing the file or folder that Opus wants the script to return the column value for.
</td></tr><tr><td>
sort</td><td>

*variant*</td><td>

Lets you control the sort order of your column by providing a *sort key* that can be different to the **value**. If provided, and the list is sorted by your column, Opus will use the value of this field to position this item rather than the **value** value.

Note that if the **[ScriptColumn](scriptcolumn.md).multicol** value is set to **True** when the column is added then this property will be found inside the **columns** **[Map](map.md)**.
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the tab that contains the item.
</td></tr><tr><td>
type</td><td>

*string*</td><td>

Lets you override the default type of the column (set via **[ScriptColumn](scriptcolumn.md).type** when the column was added) on a per-file/folder basis.  
If not specified, and no default was specified either, then columns default to plain text.  
Note that if the **[ScriptColumn](scriptcolumn.md).multicol** value is set to **True** when the column is added then this property will be found inside the **columns** **[Map](map.md)**.  
Acceptable values are: **number**: \\ \\ \\ \\ The column displays integer numbers. **double**: \\ \\ \\ \\ The column displays floating point (fractional) numbers. **size**: \\ \\ \\ \\ The column displays file sizes (automatically displays bytes, KB, MB, etc.). **zip**: \\ \\ \\ \\ The column displays file sizes (uses the settings for Zip file sizes). **graph**: \\ \\ \\ \\ The column displays a bar graph (expects a value from 0 to 100). **igraph**: \\ \\ \\ \\ The column displays an inverted bar graph. **percent**: \\ \\ \\ \\ The column displays a percentage. **date**: \\ \\ \\ \\ The column displays a date. **time**: \\ \\ \\ \\ The column displays a time. **datetime**: \\ \\ \\ \\ The column displays both a date and a time. **stars**: \\ \\ \\ \\ The column displays stars (similar to the built-in *Rating* column). The **value** should be in the form "x" or "x/y".

For *date*, *time* and *datetime* columns, you can also specify **utc** to have the values automatically converted from UTC to local time (e.g. **datetime,utc**). For *number* and *double* columns, you can also specify **signed** to have the values treated as signed rather than unsigned (e.g. **number,signed**). The options above are a subset of those you can specify via **[ScriptColumn](scriptcolumn.md).type**, since not all options make sense on a per-file/folder basis. Note that if you mix different types within the one column then the results you get when sorting by this column, or searching on your column using the **[Advanced Find](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.md)** function, may be hard to predict.
</td></tr><tr><td>
value</td><td>

*variant*</td><td>

This field is how your method returns the actual value for your column - that is, the information that is displayed to the user in this column for each file and folder.

If the type for this column has been set (either by **ScriptColumnData.type** or **[ScriptColumn](scriptcolumn.md).type**) then Opus will try to convert the provided value to the specified type. If the type is not set then Opus will treat the value as a plain text string.

If you don't provide a sort key via the **sort** field then Opus will also use this value to order the list when the list is sorted by this column.

Note that if the **[ScriptColumn](scriptcolumn.md).multicol** value is set to **True** when the column is added then this property will be found inside the **columns** **[Map](map.md)**.
</td></tr><tr><td>
userdata</td><td>

*variant*</td><td>

This returns the value associated with this column via **[ScriptColumn](scriptcolumn.md).userdata** (if any) when the column was added.

Note that if the **[ScriptColumn](scriptcolumn.md).multicol** value is set to **True** when the column is added then this property will be found inside the **columns** **[Map](map.md)**.
</td></tr></tbody>
</table>

