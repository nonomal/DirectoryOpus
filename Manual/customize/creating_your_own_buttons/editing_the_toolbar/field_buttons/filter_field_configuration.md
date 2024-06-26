# Filter Field Configuration

Changes you make to the behaviour of a [filter field](/Manual/basic_concepts/searching_and_filtering/toolbar_filter_fields.md) via its drop-down menu are not permanent - if you close the Lister and open a new one, the field will be reset to its default settings. You can change these defaults by editing the filter field in [Customize](/Manual/customize/README.md) mode.

![](/Manual/images/media/filter_field_3.png) 

Select **Customize** from the **Settings** menu, and then right-click on the filter field (it will have reverted to a simple frame - see the discussion on [Field Buttons]() for more information on this) and choose **Edit**. The **Args** field in the command editor dialog is used to provide various comma-separated keywords that define the default behaviour of the filter field. The available keywords are:

- **files**: Set the field to edit the Folder Options **Filename** filter (affects the **Show Filter** by default).
- **folders**: Set the field to edit the Folder Options **Folders** filter (affects the **Show Filter** by default).
- **both**: Set the field to edit both the Folder Options **Filename** and **Folders** filters.
- **hide**: In conjunction with any of the above three arguments, this will make the filter affect the Folder Options **Hide Filter** instead of the **Show Filter**.
- **nopartial**: Disables the **Partial Match** option.
- **norealtime**: Disables the **Filter in Real Time** option.
- **noautocontent**: Disables the **Auto-content** option.

 
