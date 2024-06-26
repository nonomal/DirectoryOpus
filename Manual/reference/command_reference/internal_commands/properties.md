# Properties

The **Properties** internal command can be used to:

- Display the system *Properties* dialog for files and folders
- Display the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** dialog for the current folder
- Display the FTP [Site Properties](/Manual/ftp/site_properties.md) dialog for the currently connected FTP site
- Display a drop-down menu of your [favorite folder formats](/Manual/basic_concepts/folder_options/folder_formats.md)
- Assign a [label](/Manual/file_operations/labels.md) to selected files and folders
- Set a selected image file as the system wallpaper image

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>

*(no argument)*</td><td>
-</td><td>
-</td><td>

Display the system *Properties* dialog for selected files and folders.

*Example:* `Properties`
</td></tr><tr><td>
ADDLABEL</td><td>
/O</td><td>

*(no value)*</td><td>

In conjunction with the **SETLABEL** argument, this lets you add one or more labels without clearing any existing ones.

*Example:* `Properties SETLABEL=Green ADDLABEL`

Can be combined with **SETLABELTOGGLE** to toggle a single label.

*Example:* `Properties SETLABEL=Bold ADDLABEL SETLABELTOGGLE`
</td></tr><tr><td>
</td><td>
</td><td>

**shift  
ctrl  
alt**</td><td>

If a keyword is specified, the labels will only be added if the specified key is held down when the function is run - otherwise the **ADDLABEL** argument will be ignored and they will replace existing labels as normal.

*Example:* `Properties SETLABEL red ADDLABEL=ctrl`
</td></tr><tr><td>
FILE</td><td>
</td><td>

*\<filename\>*</td><td>

Specifies the filename rather than using selected files. Wildcards are supported in the last path component. This is the default argument for the **Properties** command so you do not need to specify the **FILE** keyword. If the filename includes spaces make sure you enclose it in quotes.

*Example:* `Properties "C:\Windows\System32\notepad.exe"`
</td></tr><tr><td>
FOLDERFORMAT</td><td>
/S</td><td>

*(no value)*</td><td>

Display the **Folder Format** dialog for the current folder.

*Example:* `Properties FOLDERFORMAT`
</td></tr><tr><td>
FTPSITE</td><td>
/S</td><td>

*(no value)*</td><td>

Display the FTP [Site Properties](/Manual/ftp/site_properties.md) dialog for the currently connected FTP site. If you are not currently viewing an FTP directory this command has no effect.

*Example:* `Properties FTPSITE`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(no value)*</td><td>

When used with commands which generate a list of items (see [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)), the **HEADING** argument adds a small heading at the start of the list. The heading will be hidden when the list is empty. Headings only happen for commands which potentially generate multiple items at the same level as the button itself.

When **HEADING** is used by itself, without specifying a text value, the main button's label text is used for the heading.

*Example:* `Properties SETLABEL HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<heading text\>*</td><td>

You can specify the heading text if you want it to be different to the button's label.

*Example:* `Properties SETLABEL HEADING="Labels"`
</td></tr><tr><td>
LABELCATEGORY</td><td>
/K</td><td>

*\<category\>*</td><td>

When used on a command that generates a list of labels (e.g. `Properties SETLABEL` or `Properties SETLABEL !menu`) this argument lets you filter the generated list by category. It accepts one or more comma-separated wildcard strings which let you match the name of categories to include.

The specified categories will also be used when resetting labels using the `Properties SETLABEL !reset` command - if **LABELCATEGORY** is used as well, only labels in the specified categories will be cleared. This is used in the default **Properties** drop-down menu to provide a command that clears status icons without affecting other labels.

You can match uncategorized labels using the pattern **~**\* (which means "not anything").

Special handling exists for the two predefined categories, *Status* and *Colors*; these can be referenced using the English names prefixed with **raw:** and will work in any language.

*Example:* `Properties SETLABEL !menu LABELCATEGORY raw:~(Status)`
</td></tr><tr><td>
LISTER</td><td>
/S</td><td>

*(no value)*</td><td>

Displays the system *Properties* dialog for the folder currently displayed in the source file display.

*Example:* `Properties LISTER`
</td></tr><tr><td>
NOFROMFOCUS</td><td>
/S</td><td>

*(no value)*</td><td>

The default behaviour for the **Properties** command is to operate on either the source file display, or the Folder Tree, depending on which one has the input focus. This lets you use the same command to access the *Properties* dialog for folders in the tree as well as files and folders in the file display. Specify this argument to force the command to always operate on the source file display and ignore the folder tree.

*Example:* `Properties NOFROMFOCUS`
</td></tr><tr><td>
POSITION</td><td>
/K</td><td>

*\<x,y\>*</td><td>

Specify the position for the Properties dialog in screen coordinates. If no positioned specified, the dialog will open in a default position.

*Example:* `Properties POSITION=0,0`
</td></tr><tr><td>
</td><td>
</td><td>

**rel**</td><td>

Indicates the coordinates are relative to the Lister launching the Properties function.

*Example:* `Properties POSITION=32,32,rel`
</td></tr><tr><td>
</td><td>
</td><td>

**center**</td><td>

Center the properties dialog over the Lister that launched it.

*Example:* `Properties POSITION=center`
</td></tr><tr><td>
SETLABEL</td><td>
/O</td><td>

*(no value)*</td><td>

Displays a generated list of your configured [labels](/Manual/file_operations/labels.md) (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Selecting a label from this list applies it to all selected files and folders.

This command supports [embedded functions](/Manual/customize/creating_your_own_buttons/embedded_functions.md)when it's used to generate dynamic buttons.

*Example:* `Properties SETLABEL`
</td></tr><tr><td>
</td><td>
</td><td>

*\<label\>\[,\<label\>,...\]*</td><td>

Applies the specified label or labels to all selected files and folders. Multiple label names must be comma-separated. Commas and back-slashes in label names must be escaped with a back-slash.

You can combine this with the **ADDLABEL** argument to add labels to existing ones rather than replacing them. You can further combine it with **SETLABELTOGGLE** to toggle labels on and off.

The keyword **stoponmatch** can be used to add the "stop on match" flag to a file, which prevents any wildcard or label filters from applying to the file.

*Example:* `Properties SETLABEL=Green,Blue`
</td></tr><tr><td>
</td><td>
</td><td>

**!menu**</td><td>

Places the generated label list inside a menu.

*Example:* `Properties SETLABEL !menu`
</td></tr><tr><td>
</td><td>
</td><td>

**!submenu**</td><td>

Generates submenus for each label category.

*Example:* `Properties SETLABEL !submenu`
</td></tr><tr><td>
</td><td>
</td><td>

**!submenu2**</td><td>

Generates submenus for each label category, and places labels without a category in an *Uncategorized* group.

*Example:* `Properties SETLABEL !menu,!submenu2`
</td></tr><tr><td>
</td><td>
</td><td>

**!nogroup**</td><td>

Labels are grouped by category by default; specify **!nogroup** to ignore categories and generate a flat list of labels, sorted only by name, with labels from different categories intermingling.

*Example:* `Properties SETLABEL !menu,!nogroup`
</td></tr><tr><td>
</td><td>
</td><td>

**!noreset**</td><td>

A *Reset* option is normally added after an automatically generated label list. You can prevent this by specifying **!noreset**.

*Example:* `Properties SETLABEL !noreset`
</td></tr><tr><td>
</td><td>
</td><td>

**!nostoponmatch**</td><td>

A *Stop On Match* option is normally added after an automatically generated list of labels, if **Apply wildcard and filter labels to explicitly labelled files** is selected on the [Labels / Options](/Manual/preferences/preferences_categories/labels/options.md) Preferences page. You can prevent it being added by specifying **!nostoponmatch**.

*Example:* `Properties ADDLABEL SETLABELTOGGLE SETLABEL !nostoponmatch,!noreset LABELCATEGORY raw:Status`

The example above would give you top-level buttons, directly on the toolbar, to toggle each of the Status labels, with no extra buttons cluttering up the toolbar.
</td></tr><tr><td>
</td><td>
</td><td>

**!compact**</td><td>

Makes automatically generated label lists narrow and compact, where the button for each label only contains an icon or "Aa" label to show its effect. The full label names are not shown but can be revealed by hoving over each button. Intended for when you want a list of labels on a top-level toolbar without using much space.

*Example:* `Properties SETLABEL=!compact`
</td></tr><tr><td>
</td><td>
</td><td>

**!reset**</td><td>

Removes the label from all selected items. You can combine this with the **LABELCATEGORY** argument to only remove labels in certain categories.

*Example:* `Properties SETLABEL=!reset`

Note that **!reset** does not affect automatically generated label lists; a *Reset* option is added to those automatically unless **!noreset** is specified. Rather, **!reset** creates a single button which will remove any labels on the selected files.
</td></tr><tr><td>
SETLABELINFS</td><td>
/K</td><td>

**yes**</td><td>

Specify in conjunction with the **SETLABEL** argument to override the state of the **Enable label storage in the filesystem** option on the [Labels / Options](/Manual/preferences/preferences_categories/labels/options.md) Preferences page. Labels will be stored in the file system even if that option is disabled.

*Example:* `Properties SETLABEL=Green SETLABELINFS=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

The labels will be stored in your Opus configuration.

*Example:* `Properties SETLABEL=Blue SETLABELINFS=no`
</td></tr><tr><td>
SETLABELREMOVE</td><td>
/O</td><td>

*(no value)*</td><td>

Specify in conjunction with the **SETLABEL** argument to remove labels. If the targeted file or folder already has the specified label, the label will be removed. Otherwise nothing will happen.

(Only affects labels explicitly applied to individual folders and files. Labels picked up via wildcards and filters can be overridden by more explicit labels but cannot be toggled on individual items.)

*Example:* `Properties SETLABEL=Bold SETLABELREMOVE`
</td></tr><tr><td>
</td><td>
</td><td>

**shift  
ctrl  
alt**</td><td>

If specified, the **SETLABELREMOVE** argument will only apply if the specified key is held down when the function is run.

*Example:* `Properties SETLABEL=Bold SETLABELREMOVE=alt`
</td></tr><tr><td>
SETLABELTOGGLE</td><td>
/O</td><td>

*(no value)*</td><td>

Specify in conjunction with the **SETLABEL** argument to toggle labels. If the targeted file or folder already has the specified label, the entire label will be cleared instead.

(Only affects labels explicitly applied to individual folders and files. Labels picked up via wildcards and filters can be overridden by more explicit labels but cannot be toggled on individual items.)

*Example:* `Properties SETLABEL=Bold SETLABELTOGGLE`

Combine with **ADDLABEL** to toggle only a single label, while leaving any other labels the file has alone.

*Example:* `Properties SETLABEL=Red SETLABELTOGGLE ADDLABEL`
</td></tr><tr><td>
</td><td>
</td><td>

**shift  
ctrl  
alt**</td><td>

If specified, the **SETLABELTOGGLE** argument will only apply if the specified key is held down when the function is run. If the key isn't held down, the label will only be turned on - it won't be toggled off again.

*Example:* `Properties SETLABEL=Bold SETLABELTOGGLE=shift`
</td></tr><tr><td>
SETWALLPAPER</td><td>
/O</td><td>

*(no value)*</td><td>

Sets the selected image file as the system wallpaper. Opus will make a copy of the selected image file (and convert its format if necessary) - you can change where the copy is stored with the **setwallpaper_file** option on the **[Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md)** page in Preferences.

*Example:* `Properties SETWALLPAPER`
</td></tr><tr><td>
</td><td>
</td><td>

**center**</td><td>

The wallpaper mode will be set to center the image on screen.

*Example:* `Properties SETWALLPAPER=center`
</td></tr><tr><td>
</td><td>
</td><td>

**tile**</td><td>

The image will be tiled across the screen.

*Example:* `Properties SETWALLPAPER=tile`
</td></tr><tr><td>
</td><td>
</td><td>

**stretch**</td><td>

The image will be stretched (or shrunk) to fill the screen completely.

*Example:* `Properties SETWALLPAPER stretch`
</td></tr><tr><td>
</td><td>
</td><td>

**fit**</td><td>

The image will be cropped if necessary to fill the screen. The aspect ratio of the image will be preserved. This is only available on Windows 7 and above.

*Example:* `Properties SETWALLPAPER=fit`
</td></tr><tr><td>
</td><td>
</td><td>

**fill**</td><td>

The image will be stretched or shrunk to fill screen, but the aspect ratio will be preserved - and so black bars may be displayed on the sides or top and bottom of the image. This is only available on Windows 7 and above.

*Example:* `Properties SETWALLPAPER fill`
</td></tr><tr><td>
</td><td>
</td><td>

**span**</td><td>

The image will be spanned across a multiple monitor desktop. This is only available on Windows 8 and above.

*Example:* `Properties SETWALLPAPER span`
</td></tr><tr><td>
</td><td>
</td><td>

**menu**</td><td>

Displays a drop-down menu of the various wallpaper modes (acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.md)). Selecting a mode from this menu sets the selected image file as the wallpaper using that mode. This is useful when added to the context menu for the **Images** [file type group](/Manual/file_types/file_type_groups.md).

*Example:* `Properties SETWALLPAPER=menu`
</td></tr><tr><td>
SINGLE</td><td>
/S</td><td>

*(no value)*</td><td>

Modifies the behaviour of the **Properties** command when more than one file or folder is selected. By default a combined *Properties* dialog is shown for all selected items, but if **SINGLE** is specified an individual *Properties* dialog is shown for each item.

*Example:* `Properties SINGLE`
</td></tr></tbody>
</table>

