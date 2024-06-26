## Func

The **Func** object is passed to a script when it is invoked via a command. In a [script function](/Manual/scripting/script_functions.md), it is passed to the **[OnClick](../scripting_events/onclick.md)** method as the **[ClickData](clickdata.md).func** property, and in a script add-in that [adds an internal command](/Manual/scripting/example_scripts/adding_a_new_internal_command.md), via the **[ScriptCommandData](scriptcommanddata.md).func** property. The **Func** object provides information about the default source and destination of the command, as well as details about how it was invoked.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
args</td><td>

*object:***[Args](args.md)**</td><td>

Returns an **[Args](args.md)** object that provides access to any arguments given on the command line that invoked this script. This is used when the script has added an [internal command](/Manual/scripting/example_scripts/adding_a_new_internal_command.md) to Opus. A command line template can be provided when the command is added, and any arguments the user provides on the command line for the script command will be available via this object.  
For most use the **argsmap** property may be an easier way to access your command's arguments.
</td></tr><tr><td>
argsmap</td><td>

*object:***[Map](map.md)**</td><td>

Returns a **[Map](map.md)** object that provides keyword lookup for each of the arguments given on the command line. An argument will only be present in the **[Map](map.md)** if it was used on the command line, so you can easily check which arguments are present using the **[Map](map.md).exists()** method.
</td></tr><tr><td>
command</td><td>

*object:***[Command](command.md)**</td><td>

This property returns a pre-filled **[Command](command.md)** object that can be used to run commands against the source and destination tabs. Using this object is the equivalent of calling **[DOpusFactory](dopusfactory.md).Command** and setting the source and destination tabs manually.
</td></tr><tr><td>
desttab</td><td>

*object:***[Tab](tab.md)**</td><td>
This object represents the default destination tab for the function.
</td></tr><tr><td>
fromdrop</td><td>

*bool*</td><td>

Returns **True** if the command was invoked via a drag-and-drop operation.
</td></tr><tr><td>
fromkey</td><td>

*bool*</td><td>

Returns **True** if the command was invoked via the keyboard (i.e. via a hotkey rather than a button).
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

Returns a string indicating any qualifier keys that were held down by the user when the command was invoked.

The string can contain any or all of the following: *shift,* *ctrl*, *alt*, *lwin*, *rwin*.

If no qualifiers were down, the string will be: *none*
</td></tr><tr><td>
sourcetab</td><td>

*object:***[Tab](tab.md)**</td><td>
This object represents the default source tab for the function.
</td></tr><tr><td>
viewer</td><td>

*object:***[Viewer](viewer.md)**</td><td>

If this button was run from the [standalone image viewer](/Manual/additional_functionality/viewing_images/README.md), this object represents the viewer window.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Dlg</td><td>

*none*</td><td>

*object:***[Dialog](dialog.md)**</td><td>

Creates a new **[Dialog](dialog.md)** object, that lets you display dialogs and popup menus. The dialog's **window** property will be automatically assigned to the source tab.
</td></tr></tbody>
</table>

