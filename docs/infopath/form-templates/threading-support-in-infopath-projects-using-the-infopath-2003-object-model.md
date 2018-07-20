---
title: 使用 InfoPath 2003 对象模型的 InfoPath 项目中的线程支持
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- multithreading [infopath 2007], infopath 2003-compatible form templates,threading [InfoPath 2007], support for projects using InfoPath 2003 object model,InfoPath 2003-compatible form templates, threading support
localization_priority: Normal
ms.assetid: f269d64d-4102-426d-be8e-d2742a993524
description: 通过 Microsoft.Office.Interop.InfoPath.dll、Microsoft.Office.Interop.InfoPath.SemiTrust.dll 和 Microsoft.Office.Interop.InfoPath.Xml.dll 互操作程序集（由 Microsoft InfoPath 安装）访问的 COM 对象不支持在多个线程上进行调用。这包括由 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间封装的 Microsoft XML Core Services (MSXML) 对象的接口（多数接口的名称都以 IXMLDOM 开头），以及由 Microsoft.Office.Interop.InfoPath.Xml 命名空间公开的所有接口（这些接口都不是线程安全的）。
ms.openlocfilehash: 314ef57e11295c0b2dbc9866c5faa392aab055ff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774081"
---
# <a name="threading-support-in-infopath-projects-using-the-infopath-2003-object-model"></a><span data-ttu-id="3f93f-105">使用 InfoPath 2003 对象模型的 InfoPath 项目中的线程支持</span><span class="sxs-lookup"><span data-stu-id="3f93f-105">Threading Support in InfoPath Projects Using the InfoPath 2003 Object Model</span></span>

<span data-ttu-id="3f93f-106">通过 Microsoft.Office.Interop.InfoPath.dll、Microsoft.Office.Interop.InfoPath.SemiTrust.dll 和 Microsoft.Office.Interop.InfoPath.Xml.dll 互操作程序集（由 Microsoft InfoPath 安装）访问的 COM 对象不支持在多个线程上进行调用。</span><span class="sxs-lookup"><span data-stu-id="3f93f-106">The COM objects accessed through the Microsoft.Office.Interop.InfoPath.dll, Microsoft.Office.Interop.InfoPath.SemiTrust.dll, and Microsoft.Office.Interop.InfoPath.Xml.dll interop assemblies installed by Microsoft InfoPath do not support calls made on multiple threads.</span></span> <span data-ttu-id="3f93f-107">这包括由 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间封装的 Microsoft XML Core Services (MSXML) 对象的接口（多数接口的名称都以 IXMLDOM 开头），以及由 [Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/zh-CN/library/microsoft.office.interop.infopath.xml) 命名空间公开的所有接口（这些接口都不是线程安全的）。</span><span class="sxs-lookup"><span data-stu-id="3f93f-107">This includes the interfaces for Microsoft XML Core Services (MSXML) objects that are wrapped by the **Microsoft.Office.Interop.InfoPath.SemiTrust** namespace (most of which have names that are prefixed with IXMLDOM) and all of the interfaces exposed by the [Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/zh-CN/library/microsoft.office.interop.infopath.xml) namespace, none of which are thread-safe.</span></span> 
  
<span data-ttu-id="3f93f-p103">对于这些 COM 对象的所有调用都必须在一个线程上发出。InfoPath 项目中的托管代码可以创建其他线程以执行后台工作，但是在主线程以外的线程上运行的代码不能调入 InfoPath 对象模型。</span><span class="sxs-lookup"><span data-stu-id="3f93f-p103">All calls made to these COM objects must be issued on a single thread. Managed code in an InfoPath project can create other threads to perform background work, but code running on threads other than the main thread cannot call into the InfoPath object models.</span></span>
  
<span data-ttu-id="3f93f-p104">如果 InfoPath 托管代码项目使用多个线程，则在线程之间共享对象时一定要小心。不应当在线程之间共享对 XML 文档对象模型 (DOM) 或 InfoPath 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="3f93f-p104">If your InfoPath managed code project uses multiple threads, you must be careful about sharing objects between threads. No references to the XML Document Object Model (DOM) or references to InfoPath objects should be shared between threads.</span></span> 
  
## <a name="making-asynchronous-calls-to-the-infopath-object-model"></a><span data-ttu-id="3f93f-112">对 InfoPath 对象模型进行异步调用</span><span class="sxs-lookup"><span data-stu-id="3f93f-112">Making Asynchronous Calls to the InfoPath Object Model</span></span>

<span data-ttu-id="3f93f-113">如果有必要调入在单独的线程上运行的进程（如计时器），则有可能会解决 InfoPath 对象模型不支持此类调用的问题。</span><span class="sxs-lookup"><span data-stu-id="3f93f-113">For situations where it is necessary to call into a process such as a timer running on a separate thread, it is possible to work around the fact that the InfoPath object model does not support such calls.</span></span> 
  
<span data-ttu-id="3f93f-114">下面的示例在表单的 _Startup 方法中创建 **System.Timers.Timer** 实例并执行计时器的异步回调。</span><span class="sxs-lookup"><span data-stu-id="3f93f-114">The following example creates a **System.Timers.Timer** instance in the _Startup method of the form and hooks up an asynchronous callback to the timer.</span></span> <span data-ttu-id="3f93f-115">另外，还创建了窗口表单的一个不可见实例 (**System.Windows.Forms.Form**)。</span><span class="sxs-lookup"><span data-stu-id="3f93f-115">In addition, an invisible instance of the window form ( **System.Windows.Forms.Form**) is created.</span></span> <span data-ttu-id="3f93f-116">计时器的 elapsed 回调函数每秒执行一次，它在执行时将调入 Win32 **PostMessage** 函数，以便向不可见窗口发布消息。</span><span class="sxs-lookup"><span data-stu-id="3f93f-116">When the timer elapsed callback function executes once per second, it calls into the Win32 **PostMessage** function to post a message to the invisible window.</span></span> <span data-ttu-id="3f93f-117">不可见窗口具有一个 **WndProc** 函数，该函数处理它从计数器回调函数接收的消息，并更新表单的 XML 文档对象模型 (DOM)。</span><span class="sxs-lookup"><span data-stu-id="3f93f-117">The invisible window has a **WndProc** function that processes the message it receives from the timer callback function, and updates the XML document object model (DOM) of the form.</span></span> <span data-ttu-id="3f93f-118">必须将此表单作为完全信任的表单进行安装才能运行。</span><span class="sxs-lookup"><span data-stu-id="3f93f-118">This form must be installed as a fully trusted form to run.</span></span> <span data-ttu-id="3f93f-119">有关调试完全信任的表单模板的信息，请参阅[预览和调试需要完全信任的表单模板](how-to-preview-and-debug-form-templates-that-require-full-trust.md)。</span><span class="sxs-lookup"><span data-stu-id="3f93f-119">For information on debugging a fully trusted form template, see [How to: Preview and Debug Form Templates that Require Full Trust](how-to-preview-and-debug-form-templates-that-require-full-trust.md).</span></span> <span data-ttu-id="3f93f-120">有关部署完全信任的表单模板的信息，请参阅[部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="3f93f-120">For information on deploying a fully trusted form template, see [How to: Deploy InfoPath Form Templates with Code](how-to-deploy-infopath-form-templates-with-code.md).</span></span>
  
```cs
using System;
using Microsoft.Office.Interop.InfoPath.SemiTrust;
using System.Timers;
using System.Runtime.InteropServices;
// Office integration attribute. Identifies the startup class for the
// form. Do not modify.
[assembly: System.ComponentModel.DescriptionAttribute("InfoPathStartupClass, Version=1.0, Class=AsyncUpdate.AsyncUpdate")]
namespace AsyncUpdate
{
    public class User32
    {
        [DllImport("User32.dll")]
        public static extern Int32 PostMessage(
            IntPtr hWnd, int Msg, int wParam, int lParam);
        public User32()
        {    
        }
        ~User32()
        {
        }
    }
    public class MyWindow : System.Windows.Forms.Form
    {
        private XDocument thisXDocument;
        private AsyncUpdate thisProcess ;
        // Private message for internal class.
        public const int WM_MYNOTIFY = 0x400;
        public MyWindow(XDocument doc, AsyncUpdate process)
        {
            thisXDocument = doc;
            thisProcess  = process;
            this.Text = "MyWindow";
            // Force HWND to get created in Win32
            IntPtr hwnd = this.Handle; 
        }
        [System.Security.Permissions.PermissionSet(System.Security.Permissions.SecurityAction.Demand, Name="FullTrust")]
        protected override void WndProc(
            ref System.Windows.Forms.Message m) 
        {
            switch (m.Msg)
            {
            case WM_MYNOTIFY:
                IXMLDOMNode xml = thisXDocument.DOM.selectSingleNode(
                    "/my:myFields/my:field1");
                xml.text = thisProcess.counter.ToString();
                break;                
            }
            base.WndProc(ref m);
        }
    }
    // The namespace prefixes defined in this attribute must remain 
    // synchronized with those in the form definition file (.xsf).
    [InfoPathNamespace("xmlns:my='http://schemas.microsoft.com/office/infopath/2003/myXSD/2004-02-11T23-29-59'")]
    public class AsyncUpdate
    {
        private XDocument thisXDocument;
        private Application thisApplication;
        public int counter;
        private System.Timers.Timer myTimer;
        private MyWindow myWnd;
    
        public void _Startup(Application app, XDocument doc)
        {
            thisXDocument = doc;
            thisApplication = app;
            // init the counter
            counter = 0;
            // Start a timer on another thread
            myTimer = new System.Timers.Timer(1000);
            myTimer.Elapsed += new ElapsedEventHandler(
                myTimer_Elapsed);
            myTimer.Start();
            // create hidden window to receive notifications 
            // back on the main thread
            myWnd = new MyWindow(thisXDocument, this);
        }
        public void _Shutdown()
        {
            myWnd.Dispose();
            myTimer.Stop();
            myTimer.Dispose();
        }
        private void myTimer_Elapsed(object sender, ElapsedEventArgs e)
        {
            // This method is called on a second thread
            counter ++;
            // Post message back to main thread
            User32.PostMessage(
                myWnd.Handle, MyWindow.WM_MYNOTIFY, 0, 0);
        }
    }
}

```


