# 常见对话框属性

所有（或部分）控件都有若干个通用属性。

- **名称**：所有控件和对话框都有一个名称。脚本将使用此名称引用控件，例如读取或更改其值。控件名称在同一个对话框中必须唯一。添加控件后将为它分配一个默认名称，但您可能想要更改此名称，以便在脚本中更容易识别控件。
- **标题**：许多控件都有一个标题，即在用户界面中显示的字符串。对话框本身具有一个标题字符串，它显示在对话框窗口顶部的标题栏中。对于某些控件（例如编辑控件），标题字符串允许您提供控件的默认值。  
    
  在标题中使用连字符 (**&**) 为控件提供助记符（键盘加速键）。例如，**A&utomatic** 标记的 *复选框* 控件会显示为 **A<u>u</u>tomatic**，并允许用户按下 **Alt + U** 激活控件。对于 *编辑控件* 等控件（不显示标题），您可以使用单独的 *静态文本* 控件作为标记来分配助记符。如果您想在标题中显示实际的连字符，则需要将其加倍（例如 **This && That**）。
- **可见**：如果控件最初应在对话框中可见，请设置为 **True**。如果设置为 **False**，控件将不会出现，直到您在脚本中使其可见为止。
- **启用**：如果控件最初应启用（能够接收用户输入），请设置为 **True**。如果设置为 **False**，控件将处于禁用状态，直到您在脚本中启用它为止。
- **调整大小**：控制控件如何处理调整大小（如果父对话框设置为允许调整大小）。提供的选项有：
  - **X**：控件将相对于对话框的宽度移动。
  - **Y**：控件将相对于对话框的高度移动。
  - **W**：控件将相对于对话框的宽度横向（在宽度方面）增长。
  - **H**：控件将相对于对话框的高度纵向（在高度方面）增长。
  - **共享宽度**：两个或多个控件可以共享对话框的宽度。当对话框调整大小时，每个控件都会按相等量增长或缩小。
  - **共享高度**：两个或多个控件可以共享对话框的高度。当对话框调整大小时，每个控件都会按相等量增长或缩小。
  - **文本**：对于标记文本和静态控件。当与宽度调整大小结合使用时，这会导致控件自动调整其高度以显示全部文本，而其下方的控件将自动上移或下移。
- **大小写**：某些控件（如编辑控件）具有 **大小写** 属性，该属性允许您强制控件的值全部为大写或小写。
- **文本对齐**：某些控件（如编辑控件）具有此属性，该属性允许您将文本对齐从默认值（左）更改为居中或右对齐。
- **垂直对齐**：控制控件内容的垂直对齐（顶部、中部、底部）。目前仅受 *静态文本* 控件支持。