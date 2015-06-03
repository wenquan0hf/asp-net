# 广告轮转器

广告轮转控制器从一个列表里随机选择在外部 XML 定时文件中指定的横幅图像。这个外部 XML 定时文件被叫做广告文件。

广告轮转控件允许你指定一个广告文件和窗口的类型，链接应该分别遵循 AdvertisementFile 和 Target 的属性。

添加 AdRotator 的基本语法如下：

```
<asp:AdRotator  runat = "server" AdvertisementFile = "adfile.xml"  Target =  "_blank" />
```

在了解 AdRotator 控件以及它的属性之前，让我们先来看看广告文件的构成。

## 广告文件

广告文件是一种 XML 文件，它包括了广告所要被显示的信息。

可扩展标记语言（XML）是一种 W3C 的标准文本文档标记语言。它是一个基于文本的标记语言，它使您可以通过使用有意义的标签来让数据存储在结构化格式中。术语 'extensible' 意味着可以扩展功能，通过给应用程序定义有意义的标签来描述文档。

XML 本身不是一种语言，如 HTML ，而是一组用于创建新的标记语言的规则。它是一个元标记语言。它允许开发人员创建自定义标记集作特殊用途。它构建，存储并传输的信息。

下面是 XML 文件的一个例子：

```
<BOOK>
   <NAME> Learn XML </NAME>
   <AUTHOR> Samuel Peterson </AUTHOR>
   <PUBLISHER> NSS Publications </PUBLISHER>
   <PRICE> $30.00</PRICE>
</BOOK>
```

像所有的 XML 文件，该广告文件需要被具有良好定义并标记的结构化文本文件来描绘数据。这里也有一些在广告文件中常用的标准 XML 元素：

|**元素**|**描述**|
|:------------- |:-------------| 
|Advertisements|包围广告文件。|
|Ad|界定独立的广告。|
|ImageUrl|将要显示的图像的路径。|
|NavigateUrl|当用户点击该广告时出现的链接。|
|AlternateText|如果图像不能被显示，则会显示文本。|
|Keyword|关键字用来识别一组广告，用于过滤。|
|Impressions|该数字显示广告出现的频率。|
|Height|显示图像的高度。|
|Width|显示图像的宽度。|

除了这些标签，带有一般属性的习惯性的标签也可以被包含进去。下面的代码演示了一个广告文件，ads.xml：

```
<Advertisements>
   <Ad>
      <ImageUrl>rose1.jpg</ImageUrl>
      <NavigateUrl>http://www.1800flowers.com</NavigateUrl>
      <AlternateText>
         Order flowers, roses, gifts and more
      </AlternateText>
      <Impressions>20</Impressions>
      <Keyword>flowers</Keyword>
   </Ad>

   <Ad>
      <ImageUrl>rose2.jpg</ImageUrl>
      <NavigateUrl>http://www.babybouquets.com.au</NavigateUrl>
      <AlternateText>Order roses and flowers</AlternateText>
      <Impressions>20</Impressions>
      <Keyword>gifts</Keyword>
   </Ad>

   <Ad>
      <ImageUrl>rose3.jpg</ImageUrl>
      <NavigateUrl>http://www.flowers2moscow.com</NavigateUrl>
      <AlternateText>Send flowers to Russia</AlternateText>
      <Impressions>20</Impressions>
      <Keyword>russia</Keyword>
   </Ad>

   <Ad>
      <ImageUrl>rose4.jpg</ImageUrl>
      <NavigateUrl>http://www.edibleblooms.com</NavigateUrl>
      <AlternateText>Edible Blooms</AlternateText>
      <Impressions>20</Impressions>
      <Keyword>gifts</Keyword>
   </Ad>
</Advertisements>
```

## AdRotator 类的属性和事件

AdRotator 类是从 WebControl 类中派生的并且继承其属性。除了这些属性，AdRotator 类还具有以下属性：

|**属性**|**描述**|
|:------------- |:------------| 
|AdvertisementFile|广告文件的路径。|
|AlternateTextFeild|提供替代文本的域的元素名称。默认值是 Alternate Text。|
|DataMember|当不使用广告文件时，要绑定的数据的特定列表的名称。|
|DataSource|控制检索数据。|
|DataSourceID|检索数据的控制 ID。|
|Font|指定与广告横幅控件相关联的字体属性。|
|ImageUrlField|提供 URL 图像的域的名称。默认值是 ImageUrl。|
|KeywordFilter|只显示基于关键字的广告。|
|NavigateUrlField|提供要导航到的 URL 的域的元素名称。默认值是 NavigateUrl。|
|Target|显示链接的网页的内容的浏览器窗口或框架。|
|UniqueID|获得 AdRotator 控件的唯一的、以分层形式限定的标识符。|

以下是的 AdRotator 类的非常重要的事件：

|**事件**|**描述**|
|:------------- |:-------------| 
|AdCreated |每次往返服务器创建控件后，但是在页面渲染之前被触发。|
|DataBinding|当服务器控件绑定到数据源时触发。|
|DataBound|在服务器控件绑定到数据源之后发生。|
|Disposed|当服务器控件从内存释放，在服务器控件生命周期的最后一个阶段请求 ASP.NET 页时触发。|
|Init|当服务器控制被初始化时触发，其生命周期中的第一个步骤出现。|
|Load|当服务器控件加载到 Page 对象中时触发。|
|PreRender|加载 Control 对象之后，但在此之前呈现触发。|
|Unload|当服务器控件从内存中卸载时触发。|

## 使用 AdRotator 控件

创建一个新的网页，并在其上放置一个 AdRotator 控件。

```
<form id="form1" runat="server">
   <div>
      <asp:AdRotator ID="AdRotator1" runat="server" AdvertisementFile  ="~/ads.xml" onadcreated="AdRotator1_AdCreated" />
   </div>
</form>
```

该 ads.xml 文件和图像文件应该位于网站的根目录。

试着执行上述应用程序，并观察到页面每次重载时，广告都被改变。
