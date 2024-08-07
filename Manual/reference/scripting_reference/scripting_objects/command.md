# Command

The **Command** object is used by a script to run Opus commands. Any command that you can run from a button or hotkey you can run from a script - a script can even run [commands added by other scripts](/Manual/scripting/example_scripts/adding_a_new_internal_command.md). Fundamentally, using the **Command** object is similar to configuring an Opus button. You add one or more command lines to the object just the same as you add one or more command lines to a button's function. You can tell it which files and folders to act upon, and you can use the various methods and properties of the object to modify the behavior of the command. Once the object has been initialized you can use the **Run** or **RunCommand** methods to invoke the command.

A **Command** object can be created by the **[DOpusFactory](dopusfactory.md).Command** method. By default, this object has no source, destination, files to operate on, etc. - you must use the appropriate methods to configure the command before running it. You can also retrieve a **Command** object from the **[Func](func.md).command** property, and in this case the source, destination, files to operate on and several other properties are pre-initialized for you.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
deselect</td><td>

*bool*</td><td>

Set this property to **False** to prevent files used by this command from being deselected, and **True** to deselect them once the function is finished. Note that files will only be deselected if they came from a **[Tab](tab.md)** object, and only then if the command is successful.
</td></tr><tr><td>
dest</td><td>

*object:***[Path](path.md)**</td><td>

Returns a **[Path](path.md)** object that represents the destination folder of this command. If a destination tab is set, this will be the path in the tab. You can not set this property directly - instead, use either the **SetDest** or **SetDestTab** methods to change the destination folder.
</td></tr><tr><td>
desttab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object that represents the destination tab for this command (if it has one - not all commands require a destination). You can not set this property directly - instead, use the **SetDestTab** method to change the destination tab.
</td></tr><tr><td>
filecount</td><td>

*int*</td><td>

Returns the number of items in the **files** object.
</td></tr><tr><td>
files</td><td>

*object:***[Items](items.md)**</td><td>

Returns a **[Items](items.md)** object that represent the files and folders this command is to act upon. You can not modify this object directly - instead you can use the various methods (**ClearFiles**, **SetFiles**, **AddFile**, **RemoveFile**, etc.) to modify the list of items to act upon.
</td></tr><tr><td>
linecount</td><td>

*int*</td><td>
Returns the number of instruction lines added to the command.
</td></tr><tr><td>
progress</td><td>

*object:***[Progress](progress.md)**</td><td>

Returns a **[Progress](progress.md)** object that you can use to display a progress indicator to the user.
</td></tr><tr><td>
results</td><td>

*object:***[Results](results.md)**</td><td>

After every command that is run with this object, a **Results** object is available from this property. This provides information about the outcome of the command.
</td></tr><tr><td>
source</td><td>

*object:***[Path](path.md)**</td><td>

Returns a **[Path](path.md)** object that represents the source folder of this command. If a source tab is set, this will be the path in the tab. You can not set this property directly - instead, use either the **SetSource** or **SetSourceTab** methods to change the source folder.
</td></tr><tr><td>
sourcetab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object that represents the source tab for this command. You can not set this property directly - instead, use the **SetSourceTab** method to change the source tab.
</td></tr><tr><td>
vars</td><td>

*object*:**[Vars](vars.md)**</td><td>

This **[Vars](vars.md)** object represents all defined variables with *command scope* (that are scoped to this function - e.g. that were set using the **@set** directive).
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
AddFile</td><td>

\<string:path\>  
or \<**[Path:](path.md)**path\>  
or \<**[Item:](item.md)**item\></td><td>

*int*</td><td>

Adds the specified item to the collection of items this command is to act upon. You can pass the item's path as either a *string* or a **[Path](path.md)** object, and you can also pass an **[Item](item.md)** object directly.

This method returns the total number of items in the collection.
</td></tr><tr><td>
AddFiles</td><td>

*object:***[Items](items.md)**  
or ***[Vector](vector.md)**:***[Item](item.md)**  
or ***[Vector](vector.md)**:***[Path](path.md)**  
or ***[Vector](vector.md)**:string*  
or ***[StringSet](stringset.md)***  
or ***[UnorderedSet](unorderedset.md)***</td><td>

*int*</td><td>

Adds the items in the specified collection to the list of items this command is to act upon. The return value is the new number of items in the collection.

You can also pass a **[Vector](vector.md)** of **[Item](item.md)** or **[Path](path.md)** objects, or full path strings, instead of a collection. Or a **[StringSet](stringset.md)** or **[UnorderedSet](unorderedset.md)** of full path strings.
</td></tr><tr><td>
AddFilesFromClipboard</td><td>

*none*</td><td>

*int*</td><td>
Adds the contents of the clipboard to the collection of items this command is to act upon. This method supports both files and file paths copied to the clipboard as text. The return value is the new number of items in the collection.
</td></tr><tr><td>
AddFilesFromFile</td><td>

\<string:path\>  
\<string:encoding\></td><td>

*int*</td><td>

Reads file paths from the contents of the specified file and adds them to the item collection. You can provide the file's path as either a *string* or a **[Path](path.md)** object. The file must consist of one absolute path per line.  
The encoding of the file is assumed to be ANSI, unless it has a BOM (byte-order-mark) at the start, or you specify the *encoding* argument. If you specify the encoding this must be a *string* equal to one of the following: **utf16be**, **utf16le**, **utf8**, **ansi** or **cp:*XXXX*** where *XXXX* specifies the code page number).

The return value is the new number of items in the collection.
</td></tr><tr><td>
AddFilesFromFolder</td><td>

\<string:path\></td><td>

*int*</td><td>

Adds the contents of the specified folder to the collection of items this command is to act upon. You can pass the folder's path as either a *string* or a **[Path](path.md)** object. You can also append a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md) to the path to only add files matching the specified pattern.
</td></tr><tr><td>
AddLine</td><td>

\<string:instruction\></td><td>

*none*</td><td>

Adds the specified instruction line to the command that this object will run. The **AddLine** method lets you build up complicated multiple line commands - add each line in turn and then run the command using the **Run** method. For a single line command it is simpler to use the **RunCommand** method.
</td></tr><tr><td>
Clear</td><td>

*none*</td><td>

*none*</td><td>
Clears all instruction lines from the command.
</td></tr><tr><td>
ClearFailed</td><td>

*none*</td><td>

*none*</td><td>

Clears the failure flags from the **[Items](items.md)** collection. Any items that fail when a command is run will have their **failed** property set to **True**, and once this has happened the file will be skipped over by any subsequent commands. You can call this method to reset all the failure flags.
</td></tr><tr><td>
ClearFiles</td><td>

*none*</td><td>

*none*</td><td>
Clears the collection of items this command is to act upon.
</td></tr><tr><td>
ClearModifier</td><td>

\<string:modifier\></td><td>

*none*</td><td>

Clears any modifiers that have been set for this command. The supported modifiers are a subset of the full list of [command modifiers](../../command_reference/command_modifier_reference.md) - see the **SetModifier** method for a list of these. You can also pass \* to clear all modifiers that have been set.
</td></tr><tr><td>
CommandList</td><td>

*none*  
or \<string:types\></td><td>

*object:***[StringSet](stringset.md)**</td><td>

Returns a **[StringSet](stringset.md)** containing the names of all the Opus commands. You can optionally filter this set by providing one or more of the following flags as an argument to the **CommandList** method:

|       |                              |
|-------|------------------------------|
| **i** | internal (built-in) commands |
| **s** | script commands              |
| **u** | user commands                |
</td></tr><tr><td>
Dlg</td><td>

*none*</td><td>

*object:***[Dialog](dialog.md)**</td><td>

Creates a new **[Dialog](dialog.md)** object, that lets you display dialogs and popup menus. The dialog's **window** property will be automatically assigned to the source tab.
</td></tr><tr><td>
GetModifiers</td><td>

*none*</td><td>

*object:***[Map](map.md)**</td><td>

Returns a **[Map](map.md)**of the modifiers that have been set for this command (either by the **SetModifier** method, or in the case of [script add-ins](/Manual/scripting/script_add-ins/README.md) any modifiers that were set on the button that invoked the script).
</td></tr><tr><td>
IsSet</td><td>

\<string:condition\>  
\[\<string:command\>\]</td><td>

*bool*</td><td>

Returns **True** if the specified **[Set](../../command_reference/internal_commands/set.md)** command condition is true. This is the equivalent of the **@ifset** [command modifiers.](../../command_reference/command_modifier_reference.md) The optional second parameter lets you test a condition based on a command other than **Set** - for example, **IsSet("VIEWERCMD=mark", "Show")** in the viewer to test if the current image is marked.
</td></tr><tr><td>
RemoveFile</td><td>

\<string:path\>  
or \<**[Path:](path.md)**path\>  
or \<**[Item](item.md)**:item\>  
or \<int:index\></td><td>

*int*</td><td>

Removes the specified file from the **[Items](items.md)** collection. You can pass the file's path as either a *string* or a **[Path](path.md)** object. You can also pass the **[Item](item.md)** itself, or its index (starting from 0) within the collection. The return value is the new number of items in the collection.
</td></tr><tr><td>
Run</td><td>

*none*</td><td>

*int*</td><td>

Runs the command that has been built up with this object. The return value indicates whether or not the command ran successfully. Zero indicates the command could not be run or was aborted; any other number indicates the command was run for at least some files. (Note that this is not the "exit code" for external commands. For external commands it only indicates whether or not Opus launched the command. If you need the exit code of an external command, use the WScript.Shell Run or Exec methods to run the command.) You can use the **Results** property to find out more information about the results of the command, and also discover which files (if any) failed using the **failed** property of each **[Item](item.md)** in the **files** collection.
</td></tr><tr><td>
RunAsync</td><td>

*none*</td><td>

*int*</td><td>
Asynchronously runs the command that has been built up with this object, without waiting for it to return. The return value indicates whether or not the command was launched successfully, but no further information about the results of the command is available.
</td></tr><tr><td>
RunCommand</td><td>

\<string:instruction\></td><td>

*int*</td><td>

Runs the single line command given by the *instruction* argument. Calling this method is the equivalent of adding the single line with the **AddLine** method and then calling the **Run** method.
</td></tr><tr><td>
RunCommandAsync</td><td>

\<string:instruction\></td><td>

*int*</td><td>

Asynchronously runs the single line command given by the *instruction* argument, without waiting for it to return. Calling this method is the equivalent of adding the single line with the **AddLine** method and then calling the **RunAsync** method.
</td></tr><tr><td>
SetDest</td><td>

\<string:path\></td><td>

*none*</td><td>

Sets the command's destination to the specified path. You can provide the path as either a *string* or a **[Path](path.md)** object. Calling this method clears the destination tab property from the command.
</td></tr><tr><td>
SetDestTab</td><td>

\<**[Tab](tab.md)**:tab\></td><td>

*none*</td><td>

Sets the command's destination to the specified tab. The destination path will be initialized from the tab automatically (so you don't need to call **SetDest** as well as **SetDestTab**).
</td></tr><tr><td>
SetFiles</td><td>

*object:***[Items](items.md)**  
or ***[Vector](vector.md)**:***[Item](item.md)**  
or ***[Vector](vector.md)**:***[Path](path.md)**  
or ***[Vector](vector.md)**:string*  
or ***[StringSet](stringset.md)***  
or ***[UnorderedSet](unorderedset.md)***</td><td>

*none*</td><td>

Configures the command to use the files in the specified **[Items](items.md)** collection as the items the command will act upon.

You can also pass one of the other collection types, the same as with the **AddFiles** method.
</td></tr><tr><td>
SetModifier</td><td>

\<string:modifier\>  
\<string:value\></td><td>

*none*</td><td>

Turns on a modifier for this command. The supported modifiers are a subset of the full list of [command modifiers](../../command_reference/command_modifier_reference.md):  
**admin**, **async**, **codepage**, **externalonly**, **leavedoswindowopen**, **nodeselect**, **noexpandenv**, **nofilenamequoting**, **nolocalizefiles**, **noprogress**, **norunbatch**, **resolvelinks**, **runmode**.

Using this method is the equivalent of using the **AddLine** method to add the modifier to the command as an instruction; e.g. **Command.SetModifier("admin")** is the same as **Command.AddLine("@admin")**. If the modifier requires a value it is passed as the second argument, e.g. **Command.SetModifier("runmode", "hide")**.
</td></tr><tr><td>
SetProgress</td><td>

\<**[Progress](progress.md)**:progress\></td><td>

*none*</td><td>

Lets you share the progress indicator from one command with another command. You can pass this method the value of **progress** property obtained from another **Command** object.
</td></tr><tr><td>
SetQualifiers</td><td>

\<string:qualifiers\></td><td>

*none*</td><td>

This method lets you control which qualifier keys the command run by this object will consider to have been pressed when it was invoked. For example, several internal commands change their behavior when certain qualifier keys are held down - calling this method allows you to set which keys they will see.

The *qualifiers* argument must consist of one or more of the following strings (comma-separated): **none**, **shift**, **ctrl**, **alt**, **lwin**, **rwin**, **win**.
</td></tr><tr><td>
SetSource</td><td>

\<string:path\></td><td>

*none*</td><td>

Sets the command's source to the specified path. You can provide the path as either a *string* or a **[Path](path.md)** object. Calling this method clears the source tab property from the command.
</td></tr><tr><td>
SetSourceTab</td><td>

\<**[Tab](tab.md)**:tab\></td><td>

*none*</td><td>

Sets the command's source to the specified tab. The source path will be initialized from the tab automatically (so you don't need to call **SetSource** as well as **SetSourceTab**).
</td></tr><tr><td>
SetType</td><td>

\<string:type\></td><td>

*none*</td><td>

Sets the type of function that this command will run. This is equivalent to the drop-down control in the [Advanced Command Editor](/Manual/customize/creating_your_own_buttons/command_editor/advanced_command_editor.md). The *type* argument must be one of the following strings: **std**, **msdos**, **script**, **wsl**. Standard (**std**) is the default if the type is not specifically set.
</td></tr><tr><td>
UpdateToggle</td><td>

*none*</td><td>

*none*</td><td>

This method can be used to update the appearance of toolbar buttons that use variables to determine their labels or states. For example, a button might use **[@toggle:if](../../command_reference/command_modifier_reference.md)** to set its selection state based on the existence of a *global-*, *tab-* or *Lister-scoped* variable. You would call this method if you have changed such a variable from a script to force buttons that use it to update.
</td></tr></tbody>
</table>

