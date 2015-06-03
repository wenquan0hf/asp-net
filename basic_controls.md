# 基础控件

这在一章节，我们将讨论在 ASP.NET 中有效的基础控件。

## 按钮控件

ASP.NET 提供了三种不同类型的按钮控件：

- **按钮**：在矩形区域内显示文本。
- **链接按钮**：像超链接一样显示文本。
- **图像按钮**：显示图像。

当用户单击一个按钮时，两个事件被触发：单击和指令。

按钮控件的基础语法：

```
<asp:Button ID="Button1" runat="server" onclick="Button1_Click" Text="Click" / >
```

按钮控件的通用属性：

|属性|描述|
|:----|:---|
|Text|文本显示在按钮上。仅对于按钮和链环按钮的控件。|
|ImageUrl|仅对于图像按钮控件。这个图像是为了显示按钮。|
|AlternateText|仅对于图像按钮控件。如果浏览器无法显示图像，替换文本会显示。|
|CausesValidation|当用户单击按钮时确定是否执行页面验证。默认为真。|
|CommandName|当用户单击按钮时传递给命令事件的字符串值。|
|CommandArgument|当用户单击按钮时传递给命令事件的字符串值。|
|PostBackUrl|当用户单击按钮时出现需要的页面地址。|

## 文本框和标签

文本框控件是专门接受用户输入而设置。一个文本框控件可以依据文本模式的属性接受一条或多条文本的输入。

标签控件为显示文本提供了一个简单的方法，这种方法能够从执行一个页面到下一个页面。如果想要显示一个不变的文本，那么您可以使用文字文本。

正文控制的基本语法：

```
<asp:TextBox ID="txtstate" runat="server" ></asp:TextBox>
```

文本框和标签的通用属性：

|属性|描述|
|:----|:---|
|TextMode|指定文本框类型。单行模式创建标准文本，多行模式创建能够接受多个文本，口令会引发输入待标记的字符。默认为标准文本。|
|Text|文本框的文本内容。|
|MaxLength|输入文本框中文本字符的最大值。|
|Wrap|它确定多行文本框中文本是否自动换行的;默认值是真。|
|ReadOnly|确定用户是否可以更改框中的文本;默认为假，即用户可以更改文本。|
|Columns|在字符的文本框的宽度。实际宽度是基于用于文本输入的字体来确定。|
|Rows|多行文本框的高度。默认值是 0，表示一个单行文本框。|

大多使用属性的标签控件是 'Text'，它代表在标签上显示的文本。

## 复选框和单选按钮

一个复选框将显示一个选项，用户可以选中或取消。单选按钮呈现一组用户可以只选择一个选项的选项组。

如果要创建一组单选按钮，您可以为每个单选按钮组中的组名属性指定相同的名称。如果一个以上的组需要呈现一个单一的形式，则指定每个组不同的组的名称。

如果您想按照最初显示的形式来选中复选框或单选按钮，可将其选中属性为 true。如果多个单选按钮在一组的属性设置为 true，则只有最后一个被认为是 true。

复选框的基本语法：

```
<asp:CheckBox ID= "chkoption" runat= "Server"> 
</asp:CheckBox>
```

单选按钮的基本语法：

```
<asp:RadioButton ID= "rdboption" runat= "Server"> 
</asp: RadioButton>
```

复选框和单选按钮的通用属性：

|属性|描述|
|:----|:---|
|Text|在复选框或单选按钮旁边显示的文本。|
|Checked|制定是否被选中，默认为未选中。|
|GroupName|控件归属组的名称。|

## 列表控件

ASP.NET 提供以下控件：

- 下拉式列表，
- 列表框，
- 单选按钮列表，
- 复选框列表，
- 项目符号列表。

这些控件让用户可以从一个或多个项目列表中选择。列表框和下拉列表包含一个或多个列表项。这些列表可以通过代码或者由 ListItemCollection 编辑器被加载。

列表框控件的基本语法：

```
<asp:ListBox ID="ListBox1" runat="server" AutoPostBack="True"    OnSelectedIndexChanged="ListBox1_SelectedIndexChanged">
</asp:ListBox>
```

下拉列表控件的基本语法：

```
<asp:DropDownList ID="DropDownList1" runat="server" AutoPostBack="True"   OnSelectedIndexChanged="DropDownList1_SelectedIndexChanged">
</asp:DropDownList>
```

列表框和下拉列表的通用属性：

|属性|描述|
|:----|:---|
|Items|代表了控件内项目的 ListItem 对象的集合。此属性回传 ListItemCollection 类型的对象。|
|Rows|指定在框中显示的项目数。如果实际的列表中比显示的列表包含更多的行，则滚动条会被添加。|
|SelectedIndex|当前所选项目的索引。如果一个以上的项目被选择，则第一个索引选择项目。如果没有选择项目，此属性的值为 -1。|
|SelectedValue|当前选定项的值。如果一个以上的项目被选择，则第一项的值被选择。如果没有选中的项，该属性的值是一个空字符串("")。|
|SelectionMode|表示一个列表框是否允许单个选择或多个选择。|

每个列表项对象的通用属性：

|属性|描述|
|:----|:---|
|Text|为项目所显示的文本。|
|Selected|表示项目是否被选定。|
|Value|与项目相关的一串字符。|

需要重点关注的是：

- 如果您要在一个下拉列表或列表框中的项目工作，则需使用该控件的项目属性。此属性返回一个 ListItemCollection 对象，它包含该列表的所有项目。
- 当用户从下拉列表或列表框中选择一个不同的项目时，SelectedIndexChanged 事件被引发。

## ListItemCollection

ListItemCollection 对象是 ListItem 对象的集合。每个 ListItem 对象代表列表中的一个项目。在一个 ListItemCollection 中项目编号从 0 开始。

当一个列表框中的项目被加载过程中使用的字符串是比如：lstcolor.Items.Add ("Blue") 时，那么文字和列表项的值的属性设置是您指定的字符串值。为了以不同的方式设置，你必须创建一个列表项的对象，然后添加该项目到集合。

ListItemCollection 编辑器用于将项目添加到一个下拉列表或列表框。它被用来创建项目的静态列表。若要显示集合编辑器，则从智能标签菜单中选择编辑项目，或者选择控件，然后在属性窗口的项目属性中单击省略号按钮。

ListItemCollection 的通用属性：

|属性|描述|
|:----|:---|
|Item(integer)|表示在指定索引处的项目的 ListItem 对象。|
|Count|在集合中项目的个数。|

ListItemCollection 的基本方法：

|方法|描述|
|:----|:---|
|Add(string)|在集合的末端增加一个新的项目并为项目文本属性分配字符串参数。|
|Add(ListItem)|在集合末端添加一个新的项目。|
|Insert(integer, string)|在集合中指定索引位置插入项目，并为项目文本属性分配字符串参数。|
|Insert(integer, ListItem)|在集合中指定索引中的位置插入项目。|
|Remove(string)|移除与文本值相同的字符串的项目。|
|Remove(ListItem)|移除指定的项目。|
|RemoveAt(integer)|作为整数移除在指定索引中的项目。|
|Clear|移除集合中所有项目。|
|FindByValue(string)|传回与字符串值相同的项目。
FindByValue(Text)|传回与字符串文本相同的项目。|

## 单选按钮列表和复选框列表

单选按钮列表呈现互相排斥的选项列表。一个复选框列表列呈现独立选项的列表。这些控件包含 ListItem 对象的集合，它们可以通过控件的项目属性被参考。

单选按钮列表的基本语法：

```
<asp:RadioButtonList ID="RadioButtonList1" runat="server" AutoPostBack="True" 
   OnSelectedIndexChanged="RadioButtonList1_SelectedIndexChanged">
</asp:RadioButtonList>
```

复选框列表的基本语法：

```
<asp:CheckBoxList ID="CheckBoxList1" runat="server" AutoPostBack="True" 
   OnSelectedIndexChanged="CheckBoxList1_SelectedIndexChanged">
</asp:CheckBoxList>
```

复选框和单选按钮列表的通用属性：

|属性|描述|
|:----|:---|
|RepeatLayout|该属性指定在提出格式化列表过程中是否使用标签或普通 HTML 流。默认为表格。|
|RepeatDirection|它指定了方向，在该方向中控件可以被重复。可用的值是水平和垂直。默认是垂直的。|
|RepeatColumns|当重复控件时，它指定了列的数字；默认为 0。|

## 项目符号列表和编号列表

项目符号列表控件创建项目符号列表或编号列表。这些控件包含 ListItem 对象的集合，它们可以通过控件的项目属性被参考。

项目符号列表的基本语法：

```
<asp:BulletedList ID="BulletedList1" runat="server">
</asp:BulletedList>
```

项目符号列表的通用属性：

|属性|描述|
|:----|:---|
|BulletStyle|该属性指定样式和项目编号的外观或者数字。|
|RepeatDirection|它指定了方向，在该方向中控件可以被重复。可用的值是水平和垂直。默认是垂直的。|
|RepeatColumns|当重复控件时，它指定了列的数字；默认为 0。|

## 超链接控件

超链接控件就像 HTML <a> 元素。

超链接控件的基本语法：

```
<asp:HyperLink ID="HyperLink1" runat="server">
   HyperLink
</asp:HyperLink>
```

它具有以下属性：

|属性|描述|
|:----|:---|
|ImageUrl|由控件显示的图像的路径。|
|NavigateUrl|目标链接地址。|
|Text|作为链接显示的文本。|
|Target|加载链接页面的窗口或框架。|

## 图像控件

若图片无法显示，图像控件则在网页，或者一些替代文本上显示图片。

图像控件的基本语法：

```
<asp:Image ID="Image1" runat="server">
```

它具有以下重要属性：

|属性|描述|
|:----|:---|
|AlternateText|图片不存在时显示替代文本。|
|ImageAlign|对齐选项控件。|
|ImageUrl|由控件显示的图像的路径。|
