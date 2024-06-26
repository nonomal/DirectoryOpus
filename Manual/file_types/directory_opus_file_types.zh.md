# Directory Opus 文件类型

除了已注册文件类型扩展名和 [组](file_type_groups.zh.md)，Opus 还定义了一些伪文件类型。它们在 [文件类型](/Manual/file_types/README.zh.md) 对话框顶部列出。

![](/Manual/images/media/directory_opus_file_types.png) 

您对这些文件类型所做的更改将影响常规文件类型，而不是特定类型。它们是：

- **所有文件**: 属于此类别的所有文件。您对它所做的更改将影响所有类型的文件（但不包括文件夹）。
- **所有文件和文件夹**: 属于此类别的所有文件和文件夹 -您对它所做的更改将影响系统中的所有文件和文件夹。“标准”上下文菜单命令（如 **剪切**/**复制**/**粘贴**）通过此类别实现，因为这些上下文菜单命令与任何文件或文件夹相关。
- **所有文件夹**: 属于此类别命名所有文件夹。您对它所做的更改将影响所有文件夹，但对文件没有影响。
- **收藏夹项目**: 此类别会影响存储在 Opus [文件收藏夹](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 的项目。此类别的正常使用方式是添加上下文菜单项目，例如 **从收藏夹中移除**。
- **识别的图像**: 此类别包含 Opus 识别的所有图像类型。它与 **图片** 组相似，但并不相同。虽然 **图片** 组默认为包含 Opus 理解的大多数图像格式，但是您可以添加任何您喜欢的文件扩展名，而 **识别图像** 类别将自动包含所有识别的图像格式，而不包含其它格式。
- **未知文件类型**: 任何未注册文件类型都属于此类别。例如，如果您有一个名为 **myfile.bumblebee** 的文件，并且 **.bumblebee** 不是注册文件扩展名，则具有该扩展名的文件将自动属于此类别。