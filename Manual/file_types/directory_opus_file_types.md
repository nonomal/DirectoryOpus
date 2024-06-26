# Directory Opus File Types

As well as the registered file type extensions and [groups](file_type_groups.md), there are a number of pseudo-file types that Opus defines. These are listed at the top of the [File Types](/Manual/file_types/README.md) dialog.

![](/Manual/images/media/directory_opus_file_types.png) 

Changes that you make to these file types will affect general classes of file rather than specific types. They are:

- **All files**: All files belong to this class. Changes that you make to this will affect all types of file (but not folders).
- **All files and folders**: All files and folders belong to this class - changes you make to this will affect all files and folders throughout the system. The "standard" context menu commands like **Cut**/**Copy**/**Paste** are implemented through this class, as those are context menu commands that are relevant for any file or folder.
- **All folders**: All folders belong to this class. Changes that you make to this will affect all folders but have no effect on files.
- **Collection item**: This class affects items that are stored in Opus [File Collections](/Manual/basic_concepts/virtual_file_system/file_collections/README.md). The normal use of this class is to add context menu items like **Remove from Collection**.
- **Recognized images**: This class contains all image types that Opus recognizes. It's similar but not identical to the **Images** group. Although the **Images** group defaults to containing most image formats Opus understands, you can add any file extensions you like to it - whereas the **Recognized images** class automatically contains all recognized image formats and no others.
- **Unknown file types**: Any unregistered file types belong to this class. For example, if you have a file called **myfile.bumblebee** and **.bumblebee** isn't a registered file extension, files with that extension would automatically belong to this class.

 
