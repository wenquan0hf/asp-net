# ASP.NET - 指令

ASP.NET 指令是指定可选设置的说明，如注册一个自定义的控制和页面的语言。这些设置介绍了 NET Framework 如何处理单页表单(.aspx)或用户控件(.ascx)网页。

下达指令的基本语法：

```
<%@  directive_name attribute=value  [attribute=value]  %>
```

在这一部分中，我们将介绍 ASP.NET 指令，同时会在整个教程中应用大多数指令。

## 应用程序指令

应用指令定义特定应用程序的属性。它是在 global.aspx 文件的顶部提供。

应用程序指令的基本语法：

```
<%@ Application Language="C#" %>
```

应用程序指令的属性：

|属性|描述|
|:----|:---|
|Inherits|从类的名称中继承。|
|Description|应用的文本描述。解析器和编译器忽略这一点。|
|Language|应用在代码组中的语言。|

## 集合指令

集合指令链接着一个网页链接的组件或在分析时的应用程序。这可能会出现在整个应用类型链接 Global.asax 文件中，页面文件中，用于链接到另一个网页的用户控件中或用户控件中。

集合控件的基本语法是：

```
<%@ Assembly Name ="myassembly" %>
```

集合控件的属性是：

|属性|描述|
|:----|:---|
|Name|被链接的集合组件的名称。|
|Src|源文件被动态链接和编辑的路径。|

## 控制指令

控制指令是与用户控件一同使用并出现在用户控件(.ascx)文件中。

控制指令的基本语法是：

```
<%@ Control Language="C#"  EnableViewState="false" %>
```

控制指令的属性是：

|属性|描述|
|:----|:---|
|AutoEventWireup|允许或禁用事件处理程序的自动关联的布尔值。|
|ClassName|控件的文件名。|
|Debug|许或禁用编辑调试符号的布尔值。|
|Description|控制页面的文字说明，被编译器忽略。|
|EnableViewState|页面请求为是否保持视图状态的布尔值。|
|Explicit|在 VB 语言下，告知编辑器使用选项显示模式。|
|Inherits|控制页面继承的类。|
|Language|编码和脚本的语言。|
|Src|代码隐藏类的文件名。|
|Strict|在 VB 语言下，告知编辑器使用选项标准模式。|

## 工具指令

工具指令表明网页，母版页或者用户控制页必须执行具有详细说明的.Net 框架界面。

工具指令的基本语法是：

```
<%@ Implements  Interface="interface_name" %>
```

## 导入指令

导入指令导入一个命名空间到用户控制应用程序的页面。如果在 global.asax 文件中指定了 Import 指令，那么会将其应用到整个应用程序。如果它是在用户控制页面的网页中，则会将其应用到该网页或控件中。

导入指令的基本语法是：

```
<%@ namespace="System.Drawing" %>
```

## 主要指令

主要指令指定了一个页面文件作为主页。

样本主页指令的基本语法是：

```
<%@ MasterPage Language="C#"  AutoEventWireup="true"  CodeFile="SiteMater.master.cs" Inherits="SiteMaster"  %>
```

## MasterType 指令

MasterType 指令指定一个类名到页面的主属性，强化其类型。

母版式指令的基本语法是：

```
<%@ MasterType attribute="value"[attribute="value" ...]  %>
```

## 输出缓存指令

输出缓存指令控制网页或用户控件的输出缓存策略。

输出缓存指令的基本语法：

```
<%@ OutputCache Duration="15" VaryByParam="None"  %>
```

## 页面指令

页面指令定义特定的页面分析器和编译器的页面文件的属性。

页面指令的基本语法是：

```
%@ Page Language="C#"  AutoEventWireup="true" CodeFile="Default.aspx.cs"  Inherits="_Default"  Trace="true" %>
```

页面指令的属性是：

|属性|描述|
|:----|:---|
|AutoEventWireup|允许或禁用正在自动绑定到方法页面事件的布尔值;例如，Page_Load。|
|Buffer|允许或禁用 HTTP 响应缓冲的布尔值。|
|ClassName|页面的类别名称。|
|ClientTarget|服务器控件应呈现的内容的浏览器|
|CodeFile|代码隐藏文件的名称。|
|Debug|允许或禁止使用调试符号编译的布尔值。|
|Description|页面的文件说明，由解析器忽略。|
|EnableSessionState|启用或禁用页面会话状态为只读。|
|EnableViewState|允许或禁止跨页请求视图状态的布尔值。
|ErrorPage|未经处理的页面异常发生的情况下的重定地址。
|Inherits|后台代码或其他类的名称。|
|Language|代码的编程语言。
|Src|后台代码类的文件名。|
|Trace|启用或禁用跟踪。|
|TraceMode|表示跟踪信息的显示方式，并按照时间或者类别排序。|
|Transaction|表示交易是否被支持。|
|ValidateRequest|表示所有输入数据是否被有效验证为 hardcoded 列表值得布尔值。|

## 前页型指令

前页型指令为一个页面分配类别，使得该页面类型被强化。

前页型指令的样本的基本语法：

```
<%@ PreviousPageType attribute="value"[attribute="value" ...]   %>
```

## 参考指令

参考指令表明另一个页面或用户控件应编译和链接到当前页面。

参考指令的基本语法是：

```
<%@ Reference Page ="somepage.aspx" %>
```

## 注册指令

注册指令用于注册定制服务器控件和用户控件。

注册指令的基本语法是：

```
<%@ Register Src="~/footer.ascx" TagName="footer" TagPrefix="Tfooter" %>
```
