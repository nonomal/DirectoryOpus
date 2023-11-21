##### Directory Opus 13 - Detailed release notes

# Columns

- General:
  - Columns set to Fill or Collapse mode can now be temporarily resized manually.
  - If "Show friendly dates" (Preferences / File Display Columns / Options) is on, you can now choose between showing "Today", "Monday", "Tuesday", etc. for dates within the last week, or only treating "Today" specially. (Turning friendly dates off entirely means the exact date is shown in all situations.)
  - User-created columns (script and Evaluator) can now be placed in any of the standard column categories, making them closer to built-in columns. Evaluator columns can specify this in the UI and script columns can use the ScriptColumn.category property.
  - User-created columns (script and Evaluator) can have their colors changed via Preferences.
  - Date-only and time-only script columns now auto-size correctly (no longer size like wider date-time columns).
  - New "Permissions" column indicates if a file or folder's permissions are inherited from its parent or set explicitly. Can be used with Advanced Find or to create filter labels (e.g. all files with explicit permissions could be displayed in a different color, or get a status icon).
  - New columns for SHA-256, SHA-512, CRC32 and BLAKE3 hashes (in addition to older MD5 and SHA-1 ones).
  - The column list (Preferences / File Display Columns / Appearance) now tells you each column's keyword, making it easier to find and use in buttons/hotkeys.
  - The column list now lets you change colors and other properties of Shell columns.
  - The column list now groups by category, instead of being a long, flat list.
  - Any column can now be set to truncate in the middle instead of on the right. For example, "Directory Opus" might truncate to "Dire...Opus" instead of "Director...".
  - New option: "Edit ratings by clicking within the Rating column" allows the Ratings column to be read-only.
  - New option: "Show dashes in empty columns" shows "--" instead of nothing to indicate an empty column cell (where appropriate).
  - Data in individual column cells can be selected and copied to the clipboard. Hold `Ctrl`, then click or drag with the right mouse button to highlight cells. Release `Ctrl` and right-click a highlighted cell for a menu of clipboard options.
  - Within the This PC folder, the Type column now reports whether local drives are SSDs or HDDs. There's also an option to group by this.
  - Within This PC, a new "Physical Drive" column reports the physical drive number(s) a drive letter is mounted on.
  - Within This PC, the "low free space warning" (change in bar graph colour) can now be turned off, or have its threshold adjusted, via Preferences / Folders / Virtual Folders / This PC. (The colors can also be adjusted under Colors and Fonts.)
  - *Scripting:* Script columns can set their "ellipsis" property to "m" for middle truncation.
- Name Column:
  - (Configured via Preferences / File Display Columns / Filenames.)
  - Separate options to hide .lnk, .url and other file extensions (as specified in the registry).
  - Option to strip Unicode Left-to-Right (LTR) and Right-to-Left (RTL) characters from displayed names. Those characters can be used to obscure a file's real extension. We recommend turning this on if you do not need to use RTL languages.
  - Option to preserve file extensions when truncating names. For example, "Directory Opus.exe" might truncate to "Direct...exe" instead of "Directory...". (Similar to the more general middle-ellipsis option, but only keeps the extension on the right, and has no effect on folder names.)
  - (Note: These options also affect display of filenames in Thumbnails and similar modes, even thought they don't use columns.)
- Aspect Ratio:
  - Improved grouping by "Aspect Ratio", with support for more categories in both landscape and portrait orientations.
  - New "Aspect Ratio Group" column shows names like "Landscape 16:9" instead of numeric values like "1.78". (Similar to grouping by "Aspect Ratio", but displayed as a column for each file.)
- Frozen Columns:
  - In Details and Power modes, one or more columns can now be "frozen". Frozen columns remain left-aligned and do not scroll - any columns following the frozen ones will scroll beneath them.
  - *Folder Formats:* Frozen columns can now be specified, so they're always in effect in particular folders.
  - `Ctrl+Alt`+Click a column header to freeze/unfreeze it.
  - Added "Freeze Columns To Here" column header context menu.
  - Note: While a column is frozen, its position cannot be moved via drag & drop. However, it can still be resized.
  - Commands:
    - \`Set COLUMNSFREEZE\` command lets frozen columns be turned on or off via buttons/hotkeys/etc.
    - When adding columns with \`Set COLUMNSADD\` etc., an additional parameter "z" can be specified to freeze the new column (and any before it). E.g. \`Set COLUMNSADD=attr(\*,\*,\*,z)\`
  - *Scripting:* Format.frozen property returns number of frozen columns.
- Shell Properties:
  - (Configured via Preferences / File Display Columns / Shell Properties.)
  - Columns from File Explorer can now be added to Opus by simply clicking a checkbox in a list. No longer requires any scripting.
  - Drop a file on the UI to see which columns populate with useful data.
- Evaluator Columns (custom columns):
  - (Configured via Preferences / File Display Columns / Evaluator Columns.)
  - Allows you to create your own columns built using Evaluator code. Similar to script columns, but easier and with lower performance overheads.
  - One provided examples shows how to display the raw bitmap size of an image (Width x Height x Depth).
  - Another example defines a column which will show the word "Compact" for compressed files (i.e. where "disksize \< size").
  - Values from build-in columns are available as variables, allowing you to focus on logic rather than extracting data from files. For example, a column showing the modified time for files modified today, and the modified date otherwise, could be defined with a simple one-line expression.
- Evaluator Groups (custom grouping):
  - (Configured via Preferences / File Display Columns / Evaluator Groups.)
  - Existing columns can be given custom grouping schemes without having to add a separate script column, and with lower performance overheads.
  - Multiple grouping schemes can be defined for a single column, allowing different types of grouping for different situations.
  - Provided examples show how to group the Name column by the first one or two letters, the first word, the file extension, or the length of the name.
  - Examples are built using simple Evaluator code which you can adapt to group columns in different ways.
  - Folder Formats can now specify a grouping scheme, e.g. to group particular folders in a special way.
  - Commands:
    - \`Set GROUPSCHEME=...\` command can select a specific grouping scheme. With no parameters, it displays a menu of grouping modes.
    - Added \`%groupscheme%\` variable to column header context menu processing.
  - *Scripting:* Added "group_scheme" property to Tab Format script object, indicating the current grouping scheme if any.
- Grouping:
  - *Folder Formats:* Grouping options moved to a dedicated page.
  - *Commands:* New \`Set GROUPCOMBINE\` replaces older \`Set COMBINESINGLEGROUPS\` and \`Set GROUPINDIVIDUAL\`. (Old args still work, but are hidden.)
  - *Scripting:* \`Tab.format.group_combine\` property returns group-combine setting. (Old \`group_individual\` property still works but is deprecated.)
- Context menu variables:
  - These variables can be used by commands in the Column Header context menu.
  - \`%header%\` -- ID of column which was right-clicked. -1 if none (e.g. right-click space after the last column).
  - \`%headerindex%\` -- Position of header item which was right-clicked.
  - \`%headerinsert%\` -- Insertion point. Similar to %headerindex%, but +1 if the click was in the right half of the item.
  - \`%headeritem%\` -- Deprecated. The same as %headerinsert%, but the name is confusing. Kept to avoid breaking old configs.
  - \`%headername%\` -- Display name of column which was clicked. Translated into different languages.
  - \`%headerkey%\` -- Keyword of column which was clicked. Always in English, and can be passed to commands.
  - \`%group%\` -- ID of column the file display is grouping by. -1 if none.
  - \`%groupname%\` -- Display name of column the file display is grouping by. Translated.
  - \`%groupkey%\` -- Keyword of column the file display is grouping by. Always English.
  - \`%groupscheme%\` -- Keyword of current grouping scheme.
  - \`%frozenfields%\` -- Number of frozen columns. 0 if none.

------------------------------------------------------------------------

Next: [Folder Sizes](/Manual/release_history/opus13_detailed/folder_sizes.md)