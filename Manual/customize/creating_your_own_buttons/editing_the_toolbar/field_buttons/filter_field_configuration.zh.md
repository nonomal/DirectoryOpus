# 过滤器字段配置

通过下拉菜单对 [过滤器字段](/Manual/basic_concepts/searching_and_filtering/toolbar_filter_fields.zh.md) 的行为所做的更改不会保存——如果关闭文件窗口并打开一个新的文件窗口，该字段将重置为默认设置。可以通过在 [自定义](/Manual/customize/README.zh.md) 模式下编辑过滤器字段来更改这些默认设置。

![](/Manual/images/media/filter_field_3.png) 

从 **设置** 菜单中选择 **自定义**，然后右键单击过滤器字段（它将恢复到简单的帧——参见 [字段按钮]() 中的讨论了解更多相关信息），然后选择 **编辑**。命令编辑器对话框中的 **参数** 字段用于提供各种以逗号分隔的关键字，用于定义过滤器字段的默认行为。可用的关键字是：

- **文件**：将字段设置为编辑文件夹选项 **文件名** 过滤器（默认情况下影响 **显示过滤器**）。
- **文件夹**：将字段设置为编辑文件夹选项 **文件夹** 过滤器（默认情况下影响 **显示过滤器**）。
- **两者**：将字段设置为编辑文件夹选项 **文件名** 和 **文件夹** 过滤器。
- **隐藏**：结合以上任何三个参数，这将使过滤器影响文件夹选项 **隐藏过滤器** 而不是 **显示过滤器**。
- **nopartial**：禁用 **部分匹配** 选项。
- **norealtime**：禁用 **实时过滤** 选项。
- **noautocontent**：禁用 **自动内容** 选项。