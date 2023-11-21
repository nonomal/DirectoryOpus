# Favorites

The **Favorites** internal command can be used to:

- Display a dynamic list of your [Favorite folders](/Manual/basic_concepts/the_lister/navigation/favorites.md) (either all Favorites or a specific sub-branch)
- Display a dynamic list of your [SmartFavorite folders](/Manual/basic_concepts/the_lister/navigation/smartfavorites.md)
- Add a folder to your Favorites
- Create a new [folder alias](/Manual/basic_concepts/the_lister/navigation/aliases.md)
- Edit your Favorite folders (by opening Preferences to the [appropriate page](/Manual/preferences/preferences_categories/favorites_and_recent/favorites.md))

**Command Arguments:** 

| Argument | Type | Possible values | Description |
| --- | --- | --- | --- |
| *(no argument)* | - | - | Displays a dynamically generated list of your [favorite folders](/Manual/basic_concepts/the_lister/navigation/favorites.md) - you can navigate to a folder simply by selecting it from this list. Acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/RAEDME.md).<br /><br />Some of the arguments of this command can modify the appearance and behaviour of the dynamic list. Note the **PATH** argument lets you optionally specify a sub-branch of the Favorites list.<br /><br />*Example:* `Favorites` |
| ADD | /O | *(no value)* | Add the current source folder to your Favorites list. The entire path of the folder will be displayed in the Favorites list by default.<br /><br />*Example:* `Favorites ADD` |
|  |  | **nameonly** | Add the current source folder to your Favorites list, with the name of the favorite entry set to the name of the folder (so that only the name shows in the Favorites list, not the entire path).<br /><br />*Example:* `Favorites ADD=nameonly` |
|  |  | **alias** | Add or modify a folder alias instead of a favorite. You may use the **NAME** argument to specify the name of the alias, or omit it to automatically use the folder's name. You may use the **PATH** argument to specify the path the alias should point to, or omit it to automatically use the current path.<br /><br />There are two alternative syntaxes for adding an alias. Using **ADD=alias** is the same as using **ALIAS=set**, other than the behavior of the **PATH** and **NAME** arguments as noted.<br /><br />*Example:* `Favorites ADD=alias PATH "C:\Users\Jon\Documents"` |
| ADDDIALOG | /S | *(no value)* | Display a dialog that lets you edit the name and path when adding a new favorite folder.<br /><br />*Example:* `Favorites ADDDIALOG` |
| ALIAS | /K | **delete** | Deletes a folder alias. The alias name must be given by the **NAME** argument, and is not optional.<br /><br />*Example:* `Favorites ALIAS=delete NAME=MyAlias` |
|  |  | **set** | Creates or modifies a folder alias. The alias name must be given by the **NAME** argument, and the path must be given by the **PATH** argument, with neither being optional.<br /><br />*Example:* `Favorites ALIAS=set NAME=MyAlias PATH "C:\Users\Jon\Documents"` |
|  |  | **list** | Generates a dynamic list of aliases, instead of the regular Favorite list. Use this if you want a menu of your aliases which (depending on other arguments) you can click on to go to them, copy files to them, and so on.  <br />By default only your user-defined aliases are shown; use the \*\*builtin \*\*or **all** keywords to override this.<br /><br />*Example:* `Favorites ALIAS=list NOOPENINTABS SHOWICONS` |
|  |  | **builtin** | Use in conjunction with the **list** keyword to only show the large list of built-in aliases (by default only user-defined aliases are included).<br /><br />*Example:* `Favorites ALIAS=list,builtin SHOWICONS` |
|  |  | **all** | Use in conjunction with the **list** keyword to include both user-defined and built-in aliases in the list.<br /><br />*Example:* `Favorites ALIAS=list,all` |
| AUTOCREATE | /S | *\<branch path\>* | Automatically creates the branch specified by the **BRANCH** argument if it doesn't already exist. This is most commonly used by the Favorites Bar, in order to automatically create the appropriate branch of the favorites tree when the toolbar is opened.<br /><br />*Example:* `FAVORITES BRANCH="Favorites Bar" AUTOCREATE` |
| BRANCH | /K | *\<branch path\>* | Specifies a branch of the favorites tree to display, or when used with the **ADD** or **ADDDIALOG** arguments, the branch to add a new favorite to. To display the entire favorites tree or to add to the root of the favorites tree, omit the **BRANCH** argument entirely. Specify nested branches with a **\\** between each component, similar to a folder path.<br /><br />If you specify a branch where some or all parts do not exist, when used with **ADD** or **ADDDIALOG** the missing parts will be created. When used to display the favorites list, you can specify the **AUTOCREATE** argument to automatically create the branch if it doesn't already exist.<br /><br />When used with **ADDDIALOG**, the specified path will be selected by default but can then be changed when interacting with the dialog.<br /><br />*Example:* `Favorites ADD BRANCH="Test Data\Photos"` |
| COPYTO | /S | *(no value)* | Modifies the generated list of favorites, turning each item into a "copy" button that will copy selected files to the favorite folder.<br /><br />*Example:* `Favorites COPYTO` |
| EDIT | /S | *(no value)* | Display the **[Favorites and Recent / Favorites List](/Manual/preferences/preferences_categories/favorites_and_recent/favorites.md)** page in Preferences.<br /><br />*Example:* `Favorites EDIT` |
| EXCLUDEBRANCH | /K | *\<name or pattern\>* | When displaying a list of Favorites, you can use the **EXCLUDEBRANCH** argument to exclude whole branches of the favorites tree from the generated list. You can specify the full branch path, or use a [wildcard](../../wildcard_reference/pattern_matching_syntax.md).<br /><br />*Example:* `Favorites EXCLUDEBRANCH NetworkFaves` |
| FILTER | /K | *\<wildcard\>* | When displaying a list of Favorites or [SmartFavorites](/Manual/basic_concepts/the_lister/navigation/smartfavorites.md), you can use the **FILTER** argument to filter the list by path, using a [wildcard](../../wildcard_reference/pattern_matching_syntax.md). Paths which do not match the wildcard will be hidden from the generated list, and any sub-branches which become empty will also be pruned.<br /><br />\`\`Favorites SHOWICONS FILTER C:\\\`\*  <br />// Shows only paths that begin with C:\\//<br /><br />*Example:* `Favorites SHOWICONS FILTER "~(\*Program Files\*)"`  <br />// Shows only paths that do not contain Program Files.//<br /><br />To filter the list by sub-branch rather than path, see the **PATH** argument instead. |
| HEADING | /O | *(no value)* | When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/RAEDME.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.  <br />When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.<br /><br />*Example:* `Favorites SMART HEADING` |
|  |  | *\<heading text\>* | You can specify the heading text if you want it to be different to the button's label.<br /><br />*Example:* `Favorites HEADING="Best Folders"` |
| KEYARGS | /K/M | *\<qualifier:arguments\> ...* | When displaying a list of favorites, this argument lets you assign different behaviour to the items in the list if a qualifier key is held down. This is a multiple value argument - for each qualifier key combination listed, you can define a separate set of arguments that will be used when the item in the list is selected.<br /><br />For example, you could configure your favorites menu to open favorite folders in a new tab by default, but in a new Lister if the `Ctrl` key were held down.<br /><br />The qualifier part of the value consists of one or more keywords that represent the qualifier keys - **ctrl**, **shift** and **alt**. These can be combined, for example **ctrlshift** means that both the `Ctrl` and `Shift` keys must be held down. You can also use the keyword **none** to indicate arguments that are applied when no qualifiers are held.<br /><br />*Example:* `Favorites KEYARGS "ctrl:NEW" "none:NEWTAB=findexisting"` |
| MENUMARKERS | /S | *(no value)* | If the generated list of favorites includes any submenus, the top-level buttons will display a glyph indicating a dropdown menu.<br /><br />*Example:* `Favorites MENUMARKERS` |
| MOVETO | /S | *(no value)* | Modifies the generated list of favorites, turning each item into a "move" button that will move selected files to the favorite folder.<br /><br />*Example:* `Favorites MOVETO` |
| MULTIFUNC | /O | *(no value)* | The generated list of favorites will be [multiple function buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/multiple_function_buttons.md) (three-button buttons) - clicking them with the left mouse button will act as if **OPENINLEFT** were set, the right button will act as if **OPENINRIGHT** were set, and the middle mouse button will act as if **NEW** were set.<br /><br />*Example:* `Favorites MULTIFUNC` |
|  |  | **tabs** | Similar to the above except the left and right mouse button functions will open a new tab on the appropriate side of the Lister. You can control how new tabs are opened with the **NEWTAB** argument.<br /><br />*Example:* `Favorites MULTIFUNC=tabs` |
| NAME | /K | *\<name\>* | Specifies the name of the newly created favorite or alias. If a name is not provided, the name of the folder will be used by default.<br /><br />*Example:* `Favorites ADD=alias NAME=docs PATH "C:\Users\Jon\Documents"` |
| NAMESONLY | /S | *(no value)* | When listing Smart Favorites, each item in the list will only display its respective folder's name, not the full path. Full paths are displayed in tooltips instead.  <br />(The **NAMESONLY** argument does not work with the normal Favorites list, since you are free to edit item labels in that as you wish. See the **ADD=nameonly** argument, above, if you wish to automate suppression of full paths when adding normal favorites.)<br /><br />*Example:* `Favorites SMART NAMESONLY` |
| NEW | /S | *(no value)* | Favorites selected from the list generated by this command will open in a new Lister instead of the current one.<br /><br />*Example:* `Favorites NEW` |
| NEWTAB | /O | *(no value)* | Favorites selected from the list generated by this command will open in a [new tab](/Manual/basic_concepts/the_lister/tabs/RAEDME.md).<br /><br />*Example:* `Favorites NEWTAB` |
|  |  | **deflister** | If no lister exists, the Default Lister will open with an additional tab for the folder. If a lister exists, the folder will open normally in a new tab within the existing lister.<br /><br />*Example:* `Favorites NEWTAB=deflister` |
|  |  | **findexisting** | Look for the folder in an existing tab before opening a new one. If found, the existing tab will be brought to the front; otherwise a new tab will be opened. The active tab is checked first, and nothing will happen if the active tab already displays the selected path.<br /><br />*Example:* `Favorites NEWTAB=findexisting` |
|  |  | **findinactive** | Like **findexisting**, except that if the active tab already has the selected path then a new tab will be opened. Intended for buttons which switch to existing tabs to reduce clutter while retaining the ability to open a second tab for the same folder when needed.<br /><br />*Example:* `Favorites NEWTAB=findinactive` |
|  |  | **nofocus** | New tabs opened by favorites selected from the list will not be brought to the front.<br /><br />*Example:* `Favorites NEWTAB=nofocus OPENINDUAL` |
|  |  | **tofront** | If the folder was found in an existing tab, bring that tab to the front (only used with **findexisting**).<br /><br />*Example:* `Favorites NEWTAB=findexisting,tofront` |
| NOLABELS | /S | *(no value)* | The favorites list displayed by this command will not show any labels for the favorite folders. Only affects the top-level items; sub-menus will still display labels. Should be combined with **SHOWICONS**.<br /><br />*Example:* `Favorites NOLABELS SHOWICONS` |
| NOOPENINTABS | /S | *(no value)* | Do not add the **Open in tabs** command that is normally displayed at the bottom of the generated favorites list.<br /><br />*Example:* `Favorites NOOPENINTABS` |
| OPENINDEST | /S | *(no value)* | Favorites selected from the list will open in the destination file display or Lister.<br /><br />*Example:* `Favorites OPENINDEST` |
| OPENINDUAL | /S | *(no value)* | Favorites selected from the list will open in the other file display of a dual-display Lister. The Lister will be set to dual-display mode if it isn't in that mode already.<br /><br />*Example:* `Favorites OPENINDUAL` |
| OPENINLEFT | /S | *(no value)* | Favorites will open in the left-hand (or top) display of a dual-display Lister.<br /><br />*Example:* `Favorites KEYARGS none:OPENINLEFT ctrl:OPENINRIGHT` |
| OPENINRIGHT | /S | *(no value)* | Favorites will open in the right-hand (or bottom) display of a dual-display Lister.<br /><br />*Example:* `Favorites NEWTAB OPENINRIGHT` |
| PATH |  | *\<folder path\>* | When used with the **ADD** argument, specifies the path to add as a favorite or alias. Without this, the current source folder will be used.<br /><br />When used without the **ADD** argument, this modifies the dynamically generated list of favorite folders to only show the contents of a specified sub-branch of the favorites list. The branch path must be preceded with an asterisk. You can also use the **BRANCH** argument instead of this method - note that **BRANCH** does not require the asterisk in front of the branch path.<br /><br />To filter the list by path rather than sub-branch, see the **FILTER** argument.<br /><br />**PATH** is the default argument for the **Favorites** command; you do not need to specify the **PATH** keyword itself.<br /><br />*Example:* `Favorites /desktop ADD`  <br />*Example:* `Favorites \*Projects` \<nobr\>(equivalent to \`Favorites BRANCH=Projects\`)\</nobr\> |
| SHOWICONS | /S | *(no value)* | The favorites list displayed by this command will display icons for the items within it. Note that the button that contains the **Favorites** command must also have its **Show image** option turned on.<br /><br />*Example:* `Favorites SHOWICONS` |
| SMART | /O | *(no value)* | Generates a dynamic list of [SmartFavorites](/Manual/basic_concepts/the_lister/navigation/smartfavorites.md) instead of the regular Favorite list. The number of folders displayed in the list is specified on the **[Favorites and Recent / SmartFavorites](/Manual/preferences/preferences_categories/favorites_and_recent/smartfavorites.md)** Preferences page.<br /><br />*Example:* `Favorites SMART`  <br />Add the **NAMESONLY** argument to show only folder names instead of full paths, and move the full paths into tooltips.<br /><br />*Example:* `Favorites SMART NAMESONLY` |
|  |  | *\<number of items\>* | Display the specified number of SmartFavorites (overrides the number set in Preferences).<br /><br />*Example:* `Favorites SMART 20 SHOWICONS NEWTAB` |
|  |  | **clear** | Clears the SmartFavorites list, the same as clicking the option to do so within the Preferences dialog.<br /><br />*Example:* `Favorites SMART=clear` |
| USEQUALKEYS | /S | *(no value)* | Activates pre-configured behaviour for the main qualifier keys - **Control** will open the favorite folder in the dual-display, **Shift** in a new Lister and **Alt** in a new tab.<br /><br />This is equivalent to \<nobr\>\`Favorites KEYARGS ctrl:OPENINDUAL shift:NEW alt:NEWTAB\`\</nobr\>.<br /><br />*Example:* `Favorites USEQUALKEYS` |
