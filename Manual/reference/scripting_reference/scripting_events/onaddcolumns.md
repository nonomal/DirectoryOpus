# OnAddColumns

The **OnAddColumns** event is called to allow your [script add-in](/Manual/scripting/script_add-ins/README.md) to [add columns](/Manual/scripting/example_scripts/adding_a_new_column.md). Call the **[AddColData](../scripting_objects/addcoldata.md).AddColumn** method once for each column you wish to add.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnAddColumns
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[AddColData](../scripting_objects/addcoldata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

When Opus starts up, or when a script add-in is added, edited or enabled, its **OnAddColumns** method is called. This allows a script to [add columns](/Manual/scripting/example_scripts/adding_a_new_column.md) :scripting:example_scripts:adding_a_new_internal_commandto Opus. A script can reinitialize its list of columns at any time by calling the **[Script](../scripting_objects/script.md).InitColumns** method.
</td></tr></tbody>
</table>

