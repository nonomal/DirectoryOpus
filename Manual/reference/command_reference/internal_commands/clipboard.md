# Clipboard

The **Clipboard** internal command can be used to:

- Copy and paste files and folders from one folder to another
- Copy the **names** of selected files and folders to the clipboard
- Paste image or text data from the clipboard as files on disk
- Paste files, image or text data from the clipboard into archives (either new or existing)

**Command Arguments:** 

<table>
<thead><tr><th>
Argument</th><th>
Type</th><th>
Possible values</th><th>
Description
</th></tr></thead><tbody><tr><td>
ADD</td><td>
/S</td><td>
(no value)</td><td>

Adds additional files to those already on the clipboard instead of replacing them. It is used in conjunction with **COPY** or **CUT**. This lets you place multiple items on the clipboard from different source folders, and then paste them into the desired destination folder in one go.

*Example:* `Clipboard COPY ADD`
</td></tr><tr><td>
AS</td><td>
/K</td><td>

*\<filename\>*</td><td>

Overrides the default filename used when pasting images or text to disk.

Normally when you paste clipboard image data, Opus creates a file called *Clipboard Image.png* (or another suffix, depending on the file format), and when you paste text data, Opus creates a file called *Clipboard Text.txt*. Use this argument to change the filename.

If no extension is specified in the filename, the default file extension (e.g. .txt for text data) will be added automatically.

You can specify a full path to make the command always save to a particular folder instead of the current path.

This argument can also be used when pasting the clipboard contents as an archive (e.g. with **Clipboard PASTE=zip**). In this case the filename for the archive is normally generated automatically from the clipboard contents - this argument lets you override it.

*Example:* `Clipboard PASTE AS PastedData`
</td></tr><tr><td>
</td><td>
</td><td>

**ask**</td><td>

When pasting image or text data to a file, this argument causes Opus to prompt you for a name for the created file. For text you can also choose the encoding type and in the case of image data, the image format to use.

![](/Manual/images/media/paste_as.png)

This argument can also be used when pasting the clipboard contents as an archive (e.g. with **Clipboard PASTE=7z**). In this case you will be prompted for the name of the new archive and any archive format-specific parameters.

The **Shrink image to compensate for system DPI** option will scale the pasted image down if your system DPI is higher than 100%.

You can also specify the default filename to be shown in the dialog, as in the second example below.

*Example:* `Clipboard PASTE AS=ask`  
*Example:* `Clipboard PASTE AS=ask:{date|yyyy_MM}_`
</td></tr><tr><td>
COPY</td><td>
/S</td><td>

*(no value)*</td><td>

Copies all selected files and folders to the clipboard.

*Example:* `Clipboard COPY`
</td></tr><tr><td>
COPYCOMMANDARGS</td><td>
/K</td><td>

*\<arguments\>*</td><td>

When used with **Clipboard PASTE** this lets you provide additional arguments for the **Copy** command (if that's what the paste command ends up running). If the paste command doesn't use the **Copy** command (e.g. you have bitmap data on the clipboard, and an image file is created instead) then this argument is ignored.

*Example:* `Clipboard PASTE COPYCOMMANDARGS="FLATVIEWCOPY=autosingle,recreate"`
</td></tr><tr><td>
COPYIMAGE</td><td>
/S</td><td>

*(no value)*</td><td>

Copies the selected image file to the clipboard **as an image**, for pasting into other programs.

*Example:* `Clipboard COPYIMAGE`
</td></tr><tr><td>
COPYINFOTIP</td><td>
/S</td><td>

*(no value)*</td><td>

Copies the text content of the currently visible *info tip* to the clipboard. (Info tips are the "tooltips" which display information when you hover the mouse over a file or folder).

Does nothing if the lister has no visible info tip. This command only makes sense when assigned to a hotkey, since an info tip will close if you move the mouse to click on a toolbar button.

*Example:* `Clipboard COPYINFOTIP`

By default, you can also use <kbd>Ctrl+Shift+Alt+C</kbd> to do the same thing without creating a hotkey, but the command lets you give it an alternative, easier to type key. (<kbd>Ctrl+Shift+C</kbd> can also work, but is overridden by the default toolbars, which assign <kbd>Ctrl+Shift+C</kbd> to *Edit \> Copy Full Pathnames*.)
</td></tr><tr><td>
COPYNAMES</td><td>
/O</td><td>

*(no value)*</td><td>

Copies the names of all selected files and folders to the clipboard (the file names themselves are copied, in text format, rather than the actual files).

The default format (with no value specified) copies the full path and filename of all selected items to the clipboard, with one file on each line. For example,

    C:\Windows\notepad.exe
    C:\Windows\regedit.exe

The various values for the **COPYNAMES** argument let you modify the format filenames are copied in. Some values can be combined - see the examples given below for ideas on what you can do. Also see the **REGEXP** argument which lets you control the format yourself using regular expressions.

*Example:* `Clipboard COPYNAMES`
</td></tr><tr><td>
</td><td>
</td><td>

**noexts**</td><td>

Removes the extensions from file names copied to the clipboard. For example,

    C:\Windows\notepad
    C:\Windows\regedit

*Example:* `Clipboard COPYNAMES=noexts`
</td></tr><tr><td>
</td><td>
</td><td>

**nopaths**</td><td>

Copies just the names of selected items to the clipboard - the paths are not copied. For example,

    notepad.exe
    regedit.exe

*Example:* `Clipboard COPYNAMES=nopaths`  
*Example:* `Clipboard COPYNAMES=nopaths,noexts`
</td></tr><tr><td>
</td><td>
</td><td>

**url**</td><td>

Copies the names of selected items to the clipboard in URL format. For files on an FTP site this will result in an **ftp://** style path that should be accepted by other FTP programs. For local files, filenames will be copied as **file://** style links (e.g. //[file:///C:/Windows//](file:///C:/Windows//)). For example,

    file:///C:/Windows/notepad.exe
    file:///C:/Windows/regedit.exe

*Example:* `Clipboard COPYNAMES=url`
</td></tr><tr><td>
</td><td>
</td><td>

**hash**</td><td>

Copies the filename of each selected file along with its **MD5** checksum. For example,

    notepad.exe : f2c7bb8acc97f92e987a2d4087d021b1\\
    regedit.exe : 2e2c937846a0b8789e5e91739284d17a

*Example:* `Clipboard COPYNAMES=hash`
</td></tr><tr><td>
</td><td>
</td><td>

**hash2**</td><td>

Copies the **MD5** checksum of selected files in an alternative format, one compatible with the venerable *MD5Sum* utility. For example,

    f2c7bb8acc97f92e987a2d4087d021b1 *notepad.exe
    2e2c937846a0b8789e5e91739284d17a *regedit.exe

*Example:* `Clipboard COPYNAMES=hash2`
</td></tr><tr><td>
</td><td>
</td><td>

**hash3**</td><td>

Copies the **MD5** checksum of selected files **without** the filenames. You would probably only want to use this format on a single file at a time. For example,

    f2c7bb8acc97f92e987a2d4087d021b1
    2e2c937846a0b8789e5e91739284d17a

*Example:* `Clipboard COPYNAMES=hash3`
</td></tr><tr><td>
</td><td>
</td><td>

**hash4**</td><td>

Copies the filename of each selected file along with its **SHA-1** checksum. For example,

    notepad.exe : 7eb0139d2175739b3ccb0d1110067820be6abd29
    regedit.exe : f48138dc476e040b8a9925c7d2650b706178e863

*Example:* `Clipboard COPYNAMES=hash4`
</td></tr><tr><td>
</td><td>
</td><td>

**hash5**</td><td>

Copies the **SHA-1** checksum of selected files in an alternative format. For example,

    7eb0139d2175739b3ccb0d1110067820be6abd29 *notepad.exe
    f48138dc476e040b8a9925c7d2650b706178e863 *regedit.exe

*Example:* `Clipboard COPYNAMES=hash5`
</td></tr><tr><td>
</td><td>
</td><td>

**hash6**</td><td>

Copies the **SHA-1** checksum of selected files **without** the filenames. You would probably only want to use this format on a single file at a time. For example,

    7eb0139d2175739b3ccb0d1110067820be6abd29
    f48138dc476e040b8a9925c7d2650b706178e863

*Example:* `Clipboard COPYNAMES=hash6`
</td></tr><tr><td>
</td><td>
</td><td>

**hashcache**</td><td>

Add the **hashcache** keyword to one of the **hash** options to make Opus use the checksum cache; if the file has previously had its checksum calculated and does not appear to have changed, the cached value will be used.

*Example:* `Clipboard COPYNAMES=hash2,hashcache`
</td></tr><tr><td>
</td><td>
</td><td>

**unc**</td><td>

When the **unc** value is specified, and the files whose names are being copied reside on a mapped network drive, the function will resolve their mapped paths to a UNC path and copy that to the clipboard instead. For example, if **Z:** were a mapped network drive, **Clipboard COPYNAMES** would return:

    Z:\Windows\notepad.exe
    Z:\Windows\regedit.exe

Whereas **Clipboard COPYNAMES=unc** might return:

    \\win7vm\c\Windows\notepad.exe
    \\win7vm\c\Windows\regedit.exe

If the current folder is not on a mapped network drive, the unc argument has no effect.

*Example:* `Clipboard COPYNAMES=unc`
</td></tr><tr><td>
</td><td>
</td><td>

**short**</td><td>

Copies the short (8.3) versions of selected paths, rather than their long versions. For example,

    C:\PROGRA~1\GPSOFT~1\DIRECT~1\dopus.exe
    C:\PROGRA~1\GPSOFT~1\DIRECT~1\dopuslib.dll

*Example:* `Clipboard COPYNAMES=short,nopaths`

Not all drives have short paths enabled. On drives where short paths are not available, normal long paths will be copied instead.
</td></tr><tr><td>
</td><td>
</td><td>

**single**</td><td>

When multiple files are selected, this will copy all the names on a single line (separated by spaces) rather than one item per line. If any item names contain a space, they will be surrounded by quotation marks. For example,

    dopus.exe dopuslib.dll "Opus 13 What's New.pdf"

*Example:* `Clipboard COPYNAMES=nopaths,single`
</td></tr><tr><td>
</td><td>
</td><td>

**paths**</td><td>

Copies just the paths of selected items, without the filenames (the opposite of **nopaths**). For example,

    C:\Program Files\GPSoftware\Directory Opus

*Example:* `Clipboard COPYNAMES=paths`

For backward compatibility, **path** is also recognised and does the same thing.
</td></tr><tr><td>
</td><td>
</td><td>

**capsemantics**</td><td>

Makes the function behave like the Windows *Copy as path* context menu command (one file path per line, and lines are always quoted).

*Example:* `Clipboard COPYNAMES=capsemantics`
</td></tr><tr><td>
</td><td>
</td><td>

**quote**</td><td>

Forces filenames and paths copied to the clipboard to be enclosed with double-quotes even if they don't contain spaces (and therefore ordinarily wouldn't need quotes).

*Example:* `Clipboard COPYNAMES=quote`
</td></tr><tr><td>
</td><td>
</td><td>

**wsl**</td><td>

Copies file paths in WSL (Windows Subsystem for Linux) format. For example, **C:\Temp** would be converted to **/mnt/c/Temp**.

*Example:* `Clipboard COPYNAMES=wsl`
</td></tr><tr><td>
COPYQUEUE</td><td>
/O</td><td>

*(no value)*</td><td>

Use in conjunction with the **PASTE** argument to paste files with [copy queuing](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/README.md) enabled. With no value specified, copies will be queued automatically if required. This can override the **Automatically manage file copy queues** option on the **[Copying Files](/Manual/preferences/preferences_categories/file_operations/copying_files/README.md)** Preferences page.

*Example:* `Clipboard PASTE COPYQUEUE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<queue name\>*</td><td>

When you specify a queue name as the value for this argument, it enables manual copy queuing when pasting files. That is, with a name specified, file pastes will always be queued to the specified queue - if no name is specified for the argument, pastes will only be queued if needed.

*Example:* `Clipboard PASTE COPYQUEUE=MyQueue`
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

Used to disable copy queuing - whether enabled in Preferences, or otherwise enabled by the **shift** keyword.

*Example:* `Clipboard PASTE COPYQUEUE=none`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

Lets you specify two alternate parameters for the **COPYQUEUE** argument. The value specified before the **shift** keyword is used if the **Shift** key is not held down - the value after it is used if it is. For example, you could configure a paste button to queue files to a specific queue if the <kbd>Shift</kbd> key were held down, and to disable queuing otherwise.

*Example:* `Clipboard PASTE COPYQUEUE=none,shift,MyQueue`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

Specify the **quiet** keyword to suppress the prompt that normally indicates a copy operation has been queued. (Opus 13.9.1 and above: You can also turn off *Display confirmation when a job is queued* in Preferences.)

*Example:* `Clipboard PASTE COPYQUEUE=MyQueue,quiet`
</td></tr><tr><td>
</td><td>
</td><td>

**noisy**</td><td>

(Opus 13.9.1 and above.) Specify the **noisy** keyword to always show a prompt indicating a copy operation has been queued, even if *Display confirmation when a job is queued* is off in Preferences.

*Example:* `Clipboard PASTE COPYQUEUE=MyQueue,noisy`
</td></tr><tr><td>
CUT</td><td>
/S</td><td>

*(no value)*</td><td>

Cuts all selected files and folders to the clipboard (nothing happens to the files immediately, but when you paste them somewhere else they are moved rather than copied).

*Example:* `Clipboard CUT`
</td></tr><tr><td>
CUTNOCOPYQUEUEWHENSAME</td><td>
/S</td><td>

*(no value)*</td><td>

Used with **Clipboard PASTE**, this disables the use of a copy queue when the files on the clipboard are being cut (that is, moved), and the source and destination are on the same drive partition.

*Example:* `Clipboard PASTE CUTNOCOPYQUEUEWHENSAME`
</td></tr><tr><td>
EXPANDNEWLINES</td><td>
/S</td><td>

*(no value)*</td><td>

Used with **Clipboard SET**, allows you to use **\n** to insert a new line into the string, so that you can set a clipboard string consisting of multiple lines. You can also use **\\** to insert a literal backslash.

*Example:* `Clipboard EXPANDNEWLINES SET Hello\nWorld`

When inserting paths into the clipboard string while using **EXPANDNEWLINES**, you should use **[escbackslash](../external_control_codes/codes_for_passing_paths.md)** to prevent the backslashes in the paths from being misinterpreted.

*Example (all on one line):*  
**Clipboard EXPANDNEWLINES SET {sourcepath\|escbackslash}\n{destpath\|escbackslash}**
</td></tr><tr><td>
FILE</td><td>
/K/M</td><td>

*\<filename\>, ...*</td><td>

Specify the file or files to operate on. If not specified the command will operate on all currently selected files.

*Example:* `Clipboard COPY FILE "C:\moo.zip" "C:\cow.zip"`
</td></tr><tr><td>
NEWLINEIFADDING</td><td>
/S</td><td>

*(no value)*</td><td>

Used with **Clipboard ADD SET**, adds a new line between the existing clipboard data and the string to be added. If the clipboard is currently blank or has non-text data then the new line is not added.

*Example:* `Clipboard ADD NEWLINEIFADDING SET This is a new line.`
</td></tr><tr><td>
NOFROMFOCUS</td><td>
/S</td><td>

*(no value)*</td><td>

The default behaviour for the **Clipboard** command is to operate on either the source file display, or the Folder Tree, depending on which one has the input focus. This lets you use the same command to copy folders in the tree as well as files in the file display. Specify this argument to force the command to always operate on the source file display and ignore the folder tree.

*Example:* `Clipboard COPY NOFROMFOCUS`
</td></tr><tr><td>
PASTE</td><td>
/O</td><td>

*(no value)*</td><td>

Pastes any files and folders previously copied to the clipboard into the current Lister.

If the files were placed on the clipboard by a "cut" operation they will be moved, otherwise they will be copied to the new location.

Can also paste image and text data from the clipboard into new files in the current folder. When pasting image and text data, the **AS** argument can change the name and path of the created file.

*Example:* `Clipboard PASTE`
</td></tr><tr><td>
</td><td>
</td><td>

**enc:***\<encoding\>*</td><td>

Specifies the encoding type when pasting text from the clipboard to a file. The default behaviour is to paste as UTF-16 if the clipboard text is Unicode, otherwise as ANSI.

Supported encoding types are **oem**, **ansi**, **utf8**, **utf8nobom**, **utf16**, **utf16nobom**.

*Example:* `Clipboard PASTE=enc:utf8`
</td></tr><tr><td>
</td><td>
</td><td>

**jpg**</td><td>

Forces image data on the clipboard to be pasted in JPEG format (overriding the Preferences default setting). You can optionally specify the JPEG image quality, as a value from 1 to 100.

*Example:* `Clipboard PASTE=jpg:85`
</td></tr><tr><td>
</td><td>
</td><td>

**png**</td><td>

Pastes image data in PNG format. You can optionally specify the PNG compression level, as a value from 1 to 6.

*Example:* `Clipboard PASTE=png:4`
</td></tr><tr><td>
</td><td>
</td><td>

**gif**</td><td>

Pastes image data in GIF format.

*Example:* `Clipboard PASTE=gif`
</td></tr><tr><td>
</td><td>
</td><td>

**bmp**</td><td>

Pastes image data in BMP format.

*Example:* `Clipboard PASTE=bmp`
</td></tr><tr><td>
</td><td>
</td><td>

**zip**</td><td>

Pastes clipboard contents (files, image or text data) as a new ZIP archive. The filename of the archive will be generated automatically from the clipboard contents - you can override this with the **AS** argument.
</td></tr><tr><td>
</td><td>
</td><td>

**7z**</td><td>
Pastes clipboard contents as a new 7Zip archive.
</td></tr><tr><td>
</td><td>
</td><td>

*\<archive suffix\>*</td><td>
Pastes clipboard contents as a new archive of the specified type (you can specify any archive suffix that Opus supports creation of).
</td></tr><tr><td>
PASTELINK</td><td>
/O</td><td>

*(no value)*</td><td>

Pastes shortcuts to any files and folders previously copied to the clipboard into the current Lister. For example, if you use the **Clipboard COPY** command on the *C:\Windows* folder, navigate to another folder, and run the **Clipboard PASTELINK** command, it would paste a shortcut called *Windows - Shortcut.lnk*.

*Example:* `Clipboard PASTELINK`
</td></tr><tr><td>
</td><td>
</td><td>

**junction**</td><td>

Creates a junction to any folders that are on the clipboard. Junctions are only supported on NTFS volumes, and you can not create junctions to files - only folders.

*Example:* `Clipboard PASTELINK=junction`
</td></tr><tr><td>
</td><td>
</td><td>

**hardlink**</td><td>

Creates a hardlink to any files that are on the clipboard. Hardlinks are only supported on NTFS volumes, and you can not create hardlinks to folders - only to files.

*Example:* `Clipboard PASTELINK=hardlink`
</td></tr><tr><td>
</td><td>
</td><td>

**softlink**</td><td>

Creates a softlink to any files or folders that are on the clipboard. Note that the link target is stored as an absolute path. Soft links support both files and folders, but are only supported on Vista and above (and again, only on NTFS volumes). Creating a softlink requires administrator access so Opus will display a UAC prompt if necessary when you run this command.

*Example:* `Clipboard PASTELINK=softlink`
</td></tr><tr><td>
</td><td>
</td><td>

**relsoftlink**</td><td>

Creates a softlink to any files or folders that are on the clipboard, storing a relative target path if possible. A regular absolute link will be created if the target can not be expressed relative to the link.

*Example:* `Clipboard PASTELINK=relsoftlink`
</td></tr><tr><td>
</td><td>
</td><td>

**auto**</td><td>

Automatically determines the most suitable type of link to create. On Vista and above, this will be a softlink - on Windows XP, either a junction or a hardlink depending on the type of item. If a non-filesystem object is on the clipboard (e.g. you are trying to make a link to a virtual folder like the *Control Panel*) or the target drive is not formatted with NTFS then it will create a shortcut.

*Example:* `Clipboard PASTELINK=auto`
</td></tr><tr><td>
</td><td>
</td><td>

**autonosoft**</td><td>

Does the same as **auto** except that it will not try to create softlinks. In other words: It will create either a junction or a hardlink depending on the type of item. If a non-filesystem object is on the clipboard (e.g. you are trying to make a link to a virtual folder like the *Control Panel*) or the target drive is not formatted with NTFS then it will create a shortcut.

*Example:* `Clipboard PASTELINK=autonosoft`
</td></tr><tr><td>
PREFERIMAGE</td><td>
/S</td><td>

*(no value)*</td><td>

When pasting data from the clipboard into a new file, image data is normally given priority over text data. Opus makes an exception to this rule in certain situations.

For example, if you use Microsoft Excel and copy some cells to the clipboard, Excel puts both the text from the cells and a screenshot of them into the clipboard. When pasting data from Excel, people usually want the text, not the screenshot. Accordingly, when Opus detects that pasted data is from Excel it gives text priority over images, contrary to its behaviour with data from other programs.

If the **PREFERIMAGE** argument is specified, image data will *always* be given priority over text data, regardless of where the data came from. This allows you to paste the image data from Excel, if that's what you want. (You'll still get a text file if there is only text data on the clipboard.)

*Example:* `Clipboard PASTE PREFERIMAGE`
</td></tr><tr><td>
PREFERTEXT</td><td>
/S</td><td>

*(no value)*</td><td>

When pasting data from the clipboard into a new file, image data is normally given priority over text data. (There are exceptions to this rule; see the **PREFERIMAGE** argument, above.)

Normally, if another program puts both text and image data into the clipboard and you then paste in Opus to save the data into a new file, the text data will be ignored and you'll get an image file (BMP, JPG, GIF or PNG).

For example, a paint program may place both a photo and a description of the photo into the clipboard, and pasting into Opus would normally create an image file containing the photo, not a text file containing the description.

The **PREFERTEXT** argument gives text priority over images, so you'll get a text file in that situation instead. (You'll still get an image file if there is only image data on the clipboard.)

*Example:* `Clipboard PASTE PREFERTEXT`
</td></tr><tr><td>
REGEXP</td><td>
/K/M</td><td>

*\<search\> \<replace\> ...*</td><td>

In conjunction with **COPYNAMES** lets you perform [regular expression](../../wildcard_reference/regular_expression_syntax.md) manipulation on the filenames as they are put into the clipboard - effectively letting you determine your own clipboard format.

The values specified for this argument are one or more pairs of strings - the first of each pair is the pattern to search for, and the second of each pair is the replace string. For example, to strip off the suffixes of all filenames when they are copied to the clipboard, the search string would be **(.\*)\\(.\*)** and the replacement string would be **\1**.

*Example:* `Clipboard COPYNAMES=nopaths REGEXP "(.*)\\(.*)" "\1"`
</td></tr><tr><td>
SCREENSHOT</td><td>
/O</td><td>

*(no value)*</td><td>

Takes a screenshot of the active Lister and copies it to the clipboard. Equivalent to pushing <kbd>Alt+PrtScr</kbd>.

*Example:* `Clipboard SCREENSHOT`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

Takes a screenshot of the desktop and copies it to the clipboard. Equivalent to pushing <kbd>PrtScr</kbd>.

*Example:* `Clipboard SCREENSHOT=all`
</td></tr><tr><td>
</td><td>
</td><td>

**format**</td><td>

When the **save** argument is specified this lets you specify the file format to save the screenshot in. Supported formats are **jpg**, **png**, **gif** and **bmp**.

*Example:* `Clipboard SCREENSHOT=save,format:jpg`
</td></tr><tr><td>
</td><td>
</td><td>

**name**</td><td>

When the **save** argument is specified this lets you configure the name to save the screenshot to. If not specified a default name is used. You can insert the current date in the name using the **%date%** code. Remember to enclose value of the SCREENSHOT argument in quotes if your desired name contains spaces.

*Example:* `Clipboard SCREENSHOT=save,name:My_Opus_%date\\`  
*Example:* `Clipboard SCREENSHOT "save,name:Opus Screenshot"`
</td></tr><tr><td>
</td><td>
</td><td>

**quality**</td><td>

When the save argument is specified and the screenshot is saved as a jpeg image, this lets you specify the quality of the compressed image (as a value from 1 to 100).

*Example:* `Clipboard SCREENSHOT=save,format:jpg,quality:85`

If the screenshot is saved as a PNG image, you can use this to control the compression level (as a value from 1 to 6).

*Example:* `Clipboard SCREENSHOT=save,format:png,quality:4`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

Does not display a confirmation message after taking the screenshot.

*Example:* `Clipboard SCREENSHOT=all,quiet`
</td></tr><tr><td>
</td><td>
</td><td>

**save**</td><td>

The screenshot will be saved to the desktop automatically (as well as copied to the clipboard). Use the **format** and **quality** arguments to control the file type. You can configure the name with the **name** argument.

*Example:* `Clipboard SCREENSHOT=save`
</td></tr><tr><td>
</td><td>
</td><td>

**secure**</td><td>

Filenames will be blurred in the Lister when the screenshot is taken, to obscure potentially sensitive information.

*Example:* `Clipboard SCREENSHOT=all,secure`
</td></tr><tr><td>
</td><td>
</td><td>

**time**</td><td>

Displays a countdown timer before taking the screenshot.

*Example:* `Clipboard SCREENSHOT=secure,time:10`
</td></tr><tr><td>
SET</td><td>
/K/R</td><td>
user defined</td><td>

Copies the supplied text to the clipboard.

*Example:* `Clipboard SET {sourcepath}`
</td></tr><tr><td>
USESEL</td><td>
/S</td><td>

*(no value)*</td><td>

Modifies the behaviour of the **PASTE** and **PASTESHORTCUT** functions. Normally files are pasted into the current source folder. If you specify the **USESEL** argument and a sub-folder is currently selected in the source file display, the files will be pasted into that sub-folder. This is most useful when used as a context menu command (so that you can right-click on a folder and paste the clipboard contents into it).

This also works with archives that Opus can write to - for example, if you add the following command to the context menu for the *Archives* [File type Group](/Manual/file_types/file_type_groups.md) then you can right-click on an existing archive file and paste the clipboard contents directly into it.

*Example:* `Clipboard PASTE USESEL`
</td></tr></tbody>
</table>

