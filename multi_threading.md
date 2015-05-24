# ASP.NET -多线程
一个线程被定义为一个程序的执行路径。每个线程都定义了一个独特的流量控制。如果你的应用程序涉及到复杂的和耗时的操作，如数据库访问或一些激烈的 I/O 操作，那么往往设置不同的执行路径或线程，每个线程执行一个特定的工作是非常有益的。  
  
线程是轻量级的进程。使用线程的一个常见的例子是现代操作系统并行编程的的实现。使用线程节省了 CPU 周期的损失，提高了应用效率。  

到目前为止我们编译好的程序在一个线程作为一个单一的过程运行，即是应用程序的运行实例。然而，这样的应用程序只可以在某一时刻执行一个工作。让它在同一时间执行多个任务，可以把它分成更小的线程。  

在 .Net ，线程是通过 'System.Threading' 的命名空间处理的。创造的 system.threading.thread 类型的变量允许你创建一个新线程开始工作。它允许你在一个单独的线程创建和访问独立的线程。
## 创建线程
一个线程是由一个线程对象创建的，并给出了它的构造函数的开启线程的参考。 
```
    ThreadStart childthreat = new ThreadStart(childthreadcall);
```
## 线程生命周期
一个线程的生命周期开始于 system.threading.thread 类的一个对象被创建，结束于线程被终止或执行完成。  

以下是在一个线程的生命周期的各种状态：  

待开启状态：该线程的实例被创建但启动方法还未被调用的情况。  
就绪状态： 当线程准备好执行并且在等待 CPU 周期的情况。
不可运行状态：线程不能被运行的情况，有以下几种可能：  
-    当前睡眠的方法被调用  
-    等待的方法被调用  
-    被 I/O 操作阻塞   
死亡状态：线程执行完毕或已中止的情况。

## 线程优先权
Thread 类中的优先级属性主要是相对于其他线程指定一个线程的优先级。 .NET 运行时选择具有最高优先级的就绪线程。
优先权可分为：  
- 高于正常  
- 低于正常  
- 最高  
- 最低  
- 正常  

一旦一个线程被创建，系统就会使用 Thread 类的优先级设置系统设定好它的优先级。
```
    NewThread.Priority = ThreadPriority.Highest;
```

## 线程的属性和方法
线程类具有以下重要特性：  

| 属性   |描述     |
|:------------:|:----------|
|CurrentContext    |获取当前正在执行的线程的内容|
|CurrentCulture    |获取或设置当前线程的环境|
|CurrentPrinciple  |获取或设置当前进程关于基于角色的安全机制的原则|
|CurrentThread     |获取当前正在运行的线程|
|CurrentUICulture  |获取或设置当前运行的进程的资源管理器用于查找特定资源的当前环境|
|ExecutionContext  |获取包含有关当前线程的上下文信息的 ExecutionContext 对象|
|IsAlive           |获取一个值，指示当前线程的执行状态|
|IsBackground      |后台获取或设置一个值指示线程是否是后台线程|
|IsThreadPoolThread|获取一个值，指示线程是否属于托管线程池|
|ManagedThreadId   |获取托管线程的当前唯一标识符|
|Name              |获取或设置线程的名称|
|Priority          |获取或设置一个值，表示一个线程的调度优先级|
|ThreadState       |获取一个值，包含当前线程的状态 |

线程类具有以下重要方法：

| 方法  |描述   |
|:------------:|:----------|
|Abort                |调用一个 ThreadAbortException 开始终止线程的过程，调用此方法通常会终止线程。|
|AllocateDataSlot     |向所有线程分配一个未命名的数据槽。为了获得更好的性能，使用标有threadstaticattribute属性的域。|
|AllocateNamedDataSlot|向所有线程上分配已命名的数据槽。为了获得更好的性能，使用的是标有 threadstaticattribute 属性的域。|
|BeginCriticalRegion  |通知宿主执行即将进入代码区域，那里线程中止或未处理的异常的影响可能危及其他任务的应用领域。|
|BeginThreadAffinity  |通知主机托管代码将要执行，取决于当前的物理操作系统线程的标识说明。| 
|EndCriticalRegion    |通知宿主执行即将进入代码区域，那里线程中止或未处理的异常仅影响当前任务。|
|EndThreadAffinity    |通知宿主托管代码执行完成，取决于当前的物理操作系统线程的标识说明。|
|FreeNamedDataSlot    |为进程中的所有线程消除名称与槽之间的关联，为了获得更好的性能，使用的是标有 threadstaticattribute 属性的域。|
|GetData              |在当前线程的当前域从当前线程指定的插槽检索值。为了获得更好的性能，使用的是标有 threadstaticattribute 属性的域。|
|GetDomain            |返回当前域中当前正在执行的线程。|
|GetDomainID          |返回唯一的应用程序域标识符。|
|GetNamedDataSlot     |查找已命名的数据槽。为了获得更好的性能，使用的是标有 threadstaticattribute 属性的域。|
|Interrupt            |中断一个在 waitsleepjoin 线程状态的线程。|
|Join                 |阻塞调用线程，直到某个线程终止，同时继续执行标准的 COM 和 SendMessage 。该方法具有不同的重载形式。|
|MemoryBarrier        |同步内存访问如下：处理当前线程的加速器不能以存储器访问调用 memorybarrier 后先调用内存访问执行这种方式对指令重新排序。|
|ResetAbort           |取消当前线程的中止请求。|
|SetData              |设置数据在指定的时隙上当前运行的线程，该线程的当前域。为了获得更好的性能，应用领域有 threadstaticattribute 属性的域。|
|Start                |启动一个线程。|
|Sleep                |使线程暂停一个时间段。|
|SpinWait             |使线程等待的参数定义的迭代次数。|
|VolatileRead()       |读取字段的值。最新的值是由计算机的任何处理器写入，不论处理器或处理器缓存的状态数。该方法具有不同的重载形式。|
|VolatileWrite()      |立即向字段写入一个值，这样的值是对计算机中的所有处理器可见。该方法具有不同的重载形式。|
|Yield()              |使调用线程执行可以在当前的处理器运行的另一个线程，操作系统选用转向的县城|

## 具体举例
下面的例子阐明了对线程类的使用。该页面有一个控制标签显示子线程传来的消息。从主程序传来的消息直接使用 response.write（50）的方法显示出来，因此它们出现在页面的顶部。
源文件如下： 
```
    <%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="threaddemo._Default" %>
    
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
    
    <html xmlns="http://www.w3.org/1999/xhtml" >
    
       <head runat="server">
           <title>
               Untitled Page
           </title>
       </head>
       
       <body>
           <form id="form1" runat="server">
              <div>
                 <h3>Thread Example</h3>
              </div>
     
              <asp:Label ID="lblmessage" runat="server" Text="Label">
              </asp:Label>
           </form>
       </body>
       
    </html>
```
后台代码如下：
```
    using System;
    using System.Collections;
    using System.Configuration;
    using System.Data;
    using System.Linq;
    
    using System.Web;
    using System.Web.Security;
    using System.Web.UI;
    using System.Web.UI.HtmlControls;
    using System.Web.UI.WebControls;
    using System.Web.UI.WebControls.WebParts;
    
    using System.Xml.Linq;
    using System.Threading;
    
    namespace threaddemo
    {
       public partial class _Default : System.Web.UI.Page
       {
           protected void Page_Load(object sender, EventArgs e)
           {
               ThreadStart childthreat = new ThreadStart(childthreadcall);
               Response.Write("Child Thread Started <br/>");
               Thread child = new Thread(childthreat);
     
               child.Start();
     
               Response.Write("Main sleeping  for 2 seconds.......<br/>");
               Thread.Sleep(2000);
               Response.Write("<br/>Main aborting child thread<br/>");
     
               child.Abort();
           }
      
           public void childthreadcall()
           {
               try{
                   lblmessage.Text = "<br />Child thread started <br/>";
                   lblmessage.Text += "Child Thread: Coiunting to 10";
    
                   for( int i =0; i<10; i++)
                   {
                        Thread.Sleep(500);
                        lblmessage.Text += "<br/> in Child thread </br>";
                   }
    
                   lblmessage.Text += "<br/> child thread finished";
    
              }catch(ThreadAbortException e){
     
              lblmessage.Text += "<br /> child thread - exception";
    
           }finally{
              lblmessage.Text += "<br /> child thread - unable to catch the  exception";
            }
          }
       }
    }
```

##拓展

- 当页面被加载时，一个新的线程会以 childthreadcall() 为参考开始启动。主线程的活动会直接显示在网页。  
- 第二个线程运行并将消息发送到控制标签。  
- 在子线程执行时主线程休眠 2000 毫秒。
- 子线程持续运行直到它被主线程中止，然后它会抛出 ThreadAbortException 异常并被终止。  
- 控制返回到主线程。  
- 当执行时程序会发送以下信息：

![](http://www.tutorialspoint.com/asp.net/images/asp.net_thread.jpg)

