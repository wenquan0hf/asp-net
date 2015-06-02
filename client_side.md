# ASP.NET - 客户端

ASP.NET 的客户端编码有两方面：

- **客户端脚本**：它在浏览器中运行并且依次加速页面的执行。例如，客户端数据有效性能够捕捉无效数据并相应地提醒用户而不经过在服务器中回发。
- **客户端源代码**：ASP.NET 网页形成了该客户端源代码。例如，ASP.NET 网页的 HTML 源代码包含了若干隐藏区域并能自动注入 Java 描述语言代码，从而保留了信息像视图状态一样，或者进行其他工作保证网页正常运作。

## 客户端脚本

所有 ASP.NET 服务器控件都允许响应通过 Java 语言或者 VBS 语言绘制的编码。有些 ASP.NET 服务器控件端使用客户端脚本进行对用户需求的反应，而并没有回发到服务器。例如，数据有效性控件。

除了这些脚本，按钮控件器具有恰当的 OnClientClick 方法，能够在按钮单击时执行客户端脚本。

传统服务器 HTML 控件有以下几个事件能够在脚本发起时执行脚本：

|事件|属性|
|:----|:--|
|onblur|当控件失去焦点时触发|
|onfocus|当控件获得焦点触发|
|onclick|当控件被单击时触发|
|onchange|当控件值发生改变时触发|
|onkeydown|当用户按下键盘按钮时触发|
|onkeypress|当用户按下字母数字的按键时|
|onkeyup|当用户释放按键时触发|
|onmouseover|当用户移动鼠标指针在控件界面时触发|
|onserverclick|当控件界面被单击时，启动 ServerClick 事件控件|

## 客户端源代码

我们已经在以上内容中讨论过了客户端源代码。ASP.NET 网页通常被编写在两种文件中：

- 内容文件或者审定文件(.aspx)
- 代码后置的文件

内容文件包含 HTML 或者 ASP.NET 控件标签和文字来形成页面结构。代码后置的文件包含了分类定义。在运行时间，内容文件被解析并被传送到一个页面类。

这个页面类以及在编码文件中的类的定义和系统生成的编码共同组成执行编码（集成），这些集成编码加工所有的回发数据，产生响应和发回客户动作。

思考一下这个简单页面：

```
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" 
   Inherits="clientside._Default" %>

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" 
   "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<html xmlns="http://www.w3.org/1999/xhtml" >

   <head runat="server">
      <title>
         Untitled Page
      </title>
   </head>
   
   <body>
      <form id="form1" runat="server">
      
         <div>
            <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>  
            <asp:Button ID="Button1" runat="server" OnClick="Button1_Click" Text="Click" />
         </div>
         
         <hr />
         
         <h3> <asp:Label ID="Msg" runat="server" Text=""> </asp:Label> </h3>
      </form>
   </body>
   
</html>
```

当这个页面在浏览器中运行时，View Source 选项显示了 HTML 网页并通过 ASP.Net 运行时间发送到浏览器：

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" 
   "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
 
<html xmlns="http://www.w3.org/1999/xhtml" >

   <head>
      <title>
         Untitled Page
      </title>
   </head>
   
   <body>
      <form name="form1" method="post" action="Default.aspx" id="form1">
      
         <div>
            <input type="hidden" name="__VIEWSTATE" id="__VIEWSTATE" 
               value="/wEPDwUKMTU5MTA2ODYwOWRk31NudGDgvhhA7joJum9Qn5RxU2M=" />
         </div>
 
         <div>
            <input type="hidden" name="__EVENTVALIDATION"  id="__EVENTVALIDATION" 
               value="/wEWAwKpjZj0DALs0bLrBgKM54rGBhHsyM61rraxE+KnBTCS8cd1QDJ/"/>
         </div>

         <div>
            <input name="TextBox1" type="text" id="TextBox1" />  
            <input type="submit" name="Button1" value="Click" id="Button1" />
         </div>

         <hr />
         <h3><span id="Msg"></span></h3>
         
      </form>
   </body>
</html>
```

如果恰当地浏览编码，您就会发现前两个 \<div\> 标签包含了存储的视图状态和有效数据的隐藏域。
