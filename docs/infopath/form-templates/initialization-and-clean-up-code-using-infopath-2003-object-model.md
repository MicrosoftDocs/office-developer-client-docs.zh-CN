---
title: 使用 InfoPath 2003 对象模型初始化和清理代码
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, clean-up code,InfoPath 2003-compatible form templates, initialization code
localization_priority: Normal
ms.assetid: 8d19e8fa-4e5c-40bb-ae89-7a552cc7914d
description: 默认情况下，为与 InfoPath 2003 兼容的表单模板项目创建的 FormCode.cs 或 FormCode.vb 文件包含表单编程逻辑的所有源代码。项目的模板在 FormCode.cs 或 FormCode.vb 文件中生成的类与以下示例中的类非常类似，您可以在其中定义初始化和清理代码以及表单事件的处理程序。FormCode.cs 和 FormCode.vb 文件应用一个程序集级别的 System.ComponentModel.DescriptionAttribute 属性，此属性将该类标识为实现事件处理程序的唯一类。将 InfoPathNamespace 属性（由 InfoPathNamespaceAttribute 类型实现）应用于类以标识在该类内部使用的 XML DOM 选项命名空间。在 InfoPathNamespace 中引用的命名空间由 InfoPath 项目系统来维护。
ms.openlocfilehash: 1ae81c261ad9927195c0a4ac6d80f58a16a6ebf1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383119"
---
# <a name="initialization-and-clean-up-code-using-infopath-2003-object-model"></a><span data-ttu-id="8fca8-108">使用 InfoPath 2003 对象模型初始化和清理代码</span><span class="sxs-lookup"><span data-stu-id="8fca8-108">Initialization and Clean-up Code Using InfoPath 2003 Object Model</span></span>

<span data-ttu-id="8fca8-p102">默认情况下，为与 InfoPath 2003 兼容的表单模板项目创建的 FormCode.cs 或 FormCode.vb 文件包含表单编程逻辑的所有源代码。项目的模板在 FormCode.cs 或 FormCode.vb 文件中生成的类与以下示例中的类非常类似，您可以在其中定义初始化和清理代码以及表单事件的处理程序。FormCode.cs 和 FormCode.vb 文件应用一个程序集级别的 **System.ComponentModel.DescriptionAttribute** 属性，此属性将该类标识为实现事件处理程序的唯一类。将 **InfoPathNamespace** 属性（由 [InfoPathNamespaceAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathNamespaceAttribute.aspx) 类型实现）应用于类以标识在该类内部使用的 XML DOM 选项命名空间。在 **InfoPathNamespace** 中引用的命名空间由 InfoPath 项目系统来维护。</span><span class="sxs-lookup"><span data-stu-id="8fca8-p102">By default, the FormCode.cs or FormCode.vb file that is created for a form template project that is compatible with InfoPath 2003 contains all the source code for the programming logic of the form. The template for the project generates a class in the FormCode.cs or FormCode.vb file much like the classes in the following examples where you can define initialization and clean-up code, as well as handlers for form events. The FormCode.cs and FormCode.vb files apply an assembly-level **System.ComponentModel.DescriptionAttribute** attribute, which identifies the class as the only class where event handlers are implemented. The **InfoPathNamespace** attribute (which is implemented by the [InfoPathNamespaceAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathNamespaceAttribute.aspx) type) is applied to a class to identify the XML DOM selection namespaces used within the class. The namespaces referenced in the **InfoPathNamespace** are maintained by the InfoPath project system.</span></span> 
  
<span data-ttu-id="8fca8-114">FormCode 类本身提供了  `_Startup` 和  `_Shutdown` 方法，当表单打开时，除了执行标准的 InfoPath 功能以外，还可以使用这些方法为所需的任何组件执行初始化和清理例程。</span><span class="sxs-lookup"><span data-stu-id="8fca8-114">The FormCode class itself provides  `_Startup` and  `_Shutdown` methods that are used to perform initialization and clean-up routines for any components that are required in addition to standard InfoPath functionality while the form is open.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8fca8-p103">不要在  `_Startup` 和  `_Shutdown` 方法内调用 InfoPath 对象模型成员。只应当在这些方法内初始化和调用外部组件的成员。</span><span class="sxs-lookup"><span data-stu-id="8fca8-p103">Do not call members of the InfoPath object model from within the  `_Startup` and  `_Shutdown` methods. You should initialize and call only members of external components in these methods.</span></span> 
  
```cs
using System;
using Microsoft.Office.Interop.InfoPath.SemiTrust;
// Office integration attribute. Identifies the startup class for the form. Do not
// modify.
[assembly: System.ComponentModel.DescriptionAttribute(
    "InfoPathStartupClass, Version=1.0, Class=Template1.FormCode")]
namespace Template1
{
    // The namespace prefixes defined in this attribute must remain synchronized with
    // those in the form definition file (.xsf).
    [InfoPathNamespace(
        "xmlns:my='https://schemas.microsoft.com/office/infopath/2003/myXSD/2004-03-29T22-27-27'")]
    public partial class FormCode
    {
        private XDocument thisXDocument;
        private Application thisApplication;
        public void _Startup(Application app, XDocument doc)
        {
            thisXDocument = doc;
            thisApplication = app;
            // You can add additional initialization code here.
        }
        public void _Shutdown()
        {
        }
    }
}
```

```vb
Imports System
Imports Microsoft.Office.Interop.InfoPath.SemiTrust
Imports Microsoft.VisualBasic
' Office integration attribute. Identifies the startup class for the form. Do not
' modify.
<Assembly: System.ComponentModel.DescriptionAttribute( _
    "InfoPathStartupClass, Version=1.0, Class=Template1.FormCode")>
Namespace Template1
    ' The namespace prefixes defined in this attribute must remain synchronized with
    ' those in the form definition file (.xsf).
    <InfoPathNamespace( _
        "xmlns:my='https://schemas.microsoft.com/office/infopath/2003/myXSD/2004-03-29T22-36-40'")> _
    Public Class FormCode
        Private thisXDocument As XDocument
        Private thisApplication As Application
        Public Sub _Startup(app As Application, doc As XDocument)
            thisXDocument = doc
            thisApplication = app
            ' You can add additional initialization code here.
        End Sub
        Public Sub _Shutdown()
        End Sub
    End Class
End Namespace
```

## <a name="the-startup-method"></a><span data-ttu-id="8fca8-117">_Startup 方法</span><span class="sxs-lookup"><span data-stu-id="8fca8-117">The _Startup Method</span></span>

<span data-ttu-id="8fca8-p104">除了提供为其他组件编写初始化代码的位置以外， `_Startup` 方法还初始化  `thisXDocument` 和  `thisApplication` 变量，可在表单代码中使用这些变量来访问 InfoPath 对象模型中 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 和 [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) 类的成员。项目模板会自动生成初始化这两个变量所需的代码。</span><span class="sxs-lookup"><span data-stu-id="8fca8-p104">In addition to providing a place to write initialization code for additional components, the  `_Startup` method initializes the  `thisXDocument` and  `thisApplication` variables that can be used in your form code to access the members of the [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) and [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) classes in the InfoPath object model. The code necessary to initialize the two variables is generated automatically by the project template.</span></span> 
  
```cs
    private XDocument thisXDocument;
    private Application thisApplication;
    public void _Startup(Application app, XDocument doc)
    {
        thisXDocument = doc;
        thisApplication = app;
        // You can add additional initialization code here.
    }
```

```vb
    Private thisXDocument As XDocument
    Private thisApplication As Application
    Public Sub _Startup(app As Application, doc As XDocument)
        thisXDocument = doc
        thisApplication = app
        ' You can add additional initialization code here.
    End Sub

```

<span data-ttu-id="8fca8-120">下面的示例演示一个按钮的简单事件处理程序，该按钮使用  `thisXDocument` 变量访问 [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) 类型的 [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="8fca8-120">The following examples show a simple event handler for a button that uses the  `thisXDocument` variable to access the [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) method of the [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) type.</span></span> 
  
```cs
[InfoPathEventHandler(MatchPath="CTRL1_5", EventType=InfoPathEventType.OnClick)]
public void CTRL1_5_OnClick(DocActionEvent e)
{
    // Write your code here.
    thisXDocument.UI.Alert("Hello!");
}
```

```vb
<InfoPathEventHandler(MatchPath:="CTRL1_5", EventType:=InfoPathEventType.OnClick)> _
Public Sub CTRL1_5_OnClick(ByVal e As DocActionEvent)
    ' Write your code here.
    thisXDocument.UI.Alert("Hello!")
End Sub
```

<span data-ttu-id="8fca8-121">有关如何创建事件处理程序的信息，请参阅[使用 InfoPath 2003 对象模型添加事件处理程序](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="8fca8-121">For information on how to create an event handler, see [Add an Event Handler Using the InfoPath 2003 Object Model](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md).</span></span>
  
## <a name="the-shutdown-method"></a><span data-ttu-id="8fca8-122">_ShutDown 方法</span><span class="sxs-lookup"><span data-stu-id="8fca8-122">The _ShutDown Method</span></span>

<span data-ttu-id="8fca8-p105">`_Shutdown` 方法是关闭表单时调用的最后一个方法。您可以在该方法中编写清理或完成在表单中使用的组件所需的任何代码。</span><span class="sxs-lookup"><span data-stu-id="8fca8-p105">The  `_Shutdown` method is the last method called when a form is closed. You can write any code in this method that is needed to clean up or finalize components used in the form.</span></span> 
  
```cs
    public void _Shutdown()
    {
    }
```

```vb
    Public Sub _Shutdown()
    End    Sub
```

## <a name="initialization-and-clean-up-code-example"></a><span data-ttu-id="8fca8-125">初始化和清理代码示例</span><span class="sxs-lookup"><span data-stu-id="8fca8-125">Initialization and Clean-up Code Example</span></span>

<span data-ttu-id="8fca8-126">下面的示例演示如何在 `_Startup` 方法中初始化与 Microsoft SQL Server 数据库的连接以及如何在 `_Shutdown` 方法中关闭连接。</span><span class="sxs-lookup"><span data-stu-id="8fca8-126">The following example shows how to initialize a connection to a Microsoft SQL Server database in the  `_Startup` method and close the connection in the  `_Shutdown` method.</span></span> <span data-ttu-id="8fca8-127">为了使此示例正常工作，你必须先设置对 .NET Framework 的 System.Data 程序集的引用，方法是单击“项目”\*\*\*\* 菜单上的“添加引用”\*\*\*\*，然后选择 .NET\*\*\*\* 选项卡上的 System.Data.dll 组件。另请注意，`using System.Data.SqlClient`（或 `Imports System.Data.SqlClient)`）指令已添加在表单代码文件的顶部以减少击键。</span><span class="sxs-lookup"><span data-stu-id="8fca8-127">In order for this example to work correctly, you must first set a reference to the System.Data assembly of the .NET Framework by clicking **Add Reference** on the **Project** menu, and then selecting the System.Data.dll component on the **.NET** tab. Also note that the  `using System.Data.SqlClient` (or  `Imports System.Data.SqlClient)` directive was added at the top of the form code file to reduce keystrokes.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8fca8-128">包含连接到 SQL Server 数据库的表单代码的 InfoPath 表单的用户可能需要安全权限，具体取决于表单的部署方式以及安全策略的定义。</span><span class="sxs-lookup"><span data-stu-id="8fca8-128">Users of an InfoPath form that contains form code that connects to a SQL Server database may require security permissions depending on how the form is deployed and security policy is defined.</span></span> <span data-ttu-id="8fca8-129">有关安全性的详细信息，请参阅[关于具有代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)和[为具有代码的表单模板配置安全设置](how-to-configure-security-settings-for-form-templates-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="8fca8-129">For more information on security see [About the Security Model for Form Templates with Code](about-the-security-model-for-form-templates-with-code.md) and [Configure Security Settings for Form Templates with Code](how-to-configure-security-settings-for-form-templates-with-code.md).</span></span> 
  
```cs
using System;
using System.Data.SqlClient;
using Microsoft.Office.Interop.InfoPath.SemiTrust;
// Office integration attribute. Identifies the startup class for the form. Do not
// modify.
[assembly: System.ComponentModel.DescriptionAttribute(
    "InfoPathStartupClass, Version=1.0, Class=Template1.FormCode")]
namespace Template1
{
    // The namespace prefixes defined in this attribute must remain synchronized with
    // those in the form definition file (.xsf).
    [InfoPathNamespace(
        "xmlns:my='https://schemas.microsoft.com/office/infopath/2003/myXSD/2004-03-05T20-56-13'")]
    public partial class Template1
    {
        private XDocument    thisXDocument;
        private Application    thisApplication;
        private SqlConnection sqlConnect;
        public void _Startup(Application app, XDocument doc)
        {
            thisXDocument = doc;
            thisApplication = app;
            // Initialize variable for SQL Server connection.
            sqlConnect= new SqlConnection("server=localhost;Trusted_Connection=yes;database=Northwind");
        }
        public void _Shutdown()
        {
            // Close SQL Server connection at shut down.
            sqlConnect.Close();
        }
    }
}
```

```vb
Imports System
Imports System.Data.SqlClient
Imports Microsoft.Office.Interop.InfoPath.SemiTrust
Imports Microsoft.VisualBasic
' Office integration attribute. Identifies the startup class for the form. Do not
' modify.
<Assembly: System.ComponentModel.DescriptionAttribute( _
    "InfoPathStartupClass, Version=1.0, Class=Template1.FormCode")>
Namespace Template1
        ' The namespace prefixes defined in this attribute must remain synchronized with
        ' those in the form definition file (.xsf).
        <InfoPathNamespace( _
            "xmlns:my='https://schemas.microsoft.com/office/infopath/2003/myXSD/2004-03-08T18-47-33'")>        _
        Public Class Template1
            Private thisXDocument As XDocument
            Private thisApplication As Application
            Private sqlConnect As SqlConnection
            Public Sub _Startup(app As Application, doc As XDocument)
                thisXDocument = doc
                thisApplication = app
                ' Initialize variable for SQL Server connection.
                sqlConnect = New SqlConnection _("server=localhost;Trusted_Connection=yes;database=Northwind")
            End Sub
        Public Sub _Shutdown()
            ' Close SQL Server connection.
            sqlConnect.Close()
        End Sub
    End Class
End Namespace
```

## <a name="see-also"></a><span data-ttu-id="8fca8-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8fca8-130">See also</span></span>



[<span data-ttu-id="8fca8-131">使用 InfoPath 2003 对象模型添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="8fca8-131">Add an Event Handler Using the InfoPath 2003 Object Model</span></span>](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)

