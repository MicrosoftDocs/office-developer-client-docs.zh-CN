---
title: 使用 InfoPath 2003 对象模型处理表单窗口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, form windows,form windows [InfoPath 2007], InfoPath 2003-compatible form templates
localization_priority: Normal
ms.assetid: fbcf3a04-ee0f-40a6-8edd-583ae203e2e1
description: 以编程方式处理 InfoPath 表单时，您可以编写代码来访问该表单的窗口，然后自定义窗口中包含的某些项目。通过结合使用 WindowObject 接口和 WindowsCollection 接口，InfoPath 2003 兼容对象模型支持对表单的窗口进行访问。
ms.openlocfilehash: f8939fc562cf16c1bce0f6f88bba659e895254f3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299893"
---
# <a name="work-with-form-windows-using-the-infopath-2003-object-model"></a>使用 InfoPath 2003 对象模型处理表单窗口

以编程方式处理 InfoPath 表单时，您可以编写代码来访问该表单的窗口，然后自定义窗口中包含的某些项目。通过结合使用 [WindowObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WindowObject.aspx) 接口和 [WindowsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WindowsCollection.aspx) 接口，InfoPath 2003 兼容对象模型支持对表单的窗口进行访问。 
  
InfoPath 中有两类窗口：
  
- 用户在填写表单时使用的编辑窗口。
    
- 用户在设计表单模板时使用的设计窗口。
    
在表单模板中编写代码时，编辑窗口提供了最有用的功能，因为您可以使用引用该窗口的 **WindowObject** 实例来访问可用来自定义表单编辑体验的各种属性和方法。 
  
## <a name="overview-of-the-windowscollection-interface"></a>WindowsCollection 接口概述

**WindowsCollection** 接口提供了下列属性，表单模板开发人员可将其用于管理该表单包含的 **WindowObject** 实例。 
  
|**名称**|**说明**|
|:-----|:-----|
|[Count](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Windows.Count.aspx) 属性  <br/> |返回集合中包含的 **Window** 对象的数目。  <br/> |
|[Item](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Windows.Item.aspx) 属性  <br/> |返回对指定的 **Window** 对象的引用。  <br/> **注意**：Visual C# 使用索引器而不是通过调用 **Item** 属性来访问集合。 例如，`thisApplication.Windows[0].Caption`。           |
   
## <a name="overview-of-the-window-object"></a>Window 对象概述

**WindowObject** 接口提供了下列方法和属性，表单开发人员可以使用这些属性和方法与 InfoPath 窗口进行交互。 根据所使用的窗口类型 ([XdWindowType](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XdWindowType.aspx)) 的不同，对这些方法和属性的支持也不同。 有些方法和属性只适用于编辑器窗口类型 (**XdWindowType.xdEditorWindow**)。 有些方法和属性既适用于编辑器窗口类型，也适用于设计器窗口类型 (**XdWindowType.xdDesignerWindow**)。 此外，与所有 InfoPath 对象模型成员一样，当从表单模板调用时，根据安全级别和表单部署方式的不同，对方法和属性的支持也有所不同。
  
|**名称**|**说明**|**窗口类型支持**|
|:-----|:-----|:-----|
|[Activate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.Activate.aspx) 方法  <br/> |指定该窗口为当前的活动窗口。  <br/> |**xdDesignWindow** 和 **xdEditorWindow** 类型  <br/> |
|[Active](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.Active.aspx) 属性  <br/> |返回一个 **Boolean** 值，指示窗口是否是当前的活动窗口。  <br/> |**xdDesignWindow** 和 **xdEditorWindow** 类型  <br/> |
|[Caption](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.Caption.aspx) 属性  <br/> |读/写属性，用于返回或设置 **Window** 对象所代表的窗口的标题文本。  <br/> |仅限于 **xdEditorWindow** 类型  <br/> |
|[Close](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.Close.aspx) 方法  <br/> |关闭窗口。  <br/> |仅限于 **xdEditorWindow** 类型  <br/> |
|[CommandBars](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.CommandBars.aspx) 属性  <br/> |返回一个对 Microsoft Office **CommandBars** 对象的引用。  <br/> |**xdDesignWindow** 和 **xdEditorWindow** 类型  <br/> |
|[Height](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.Height.aspx) 属性  <br/> |长整型的读/写属性，用于指定 **Window** 对象所代表的窗口的高度（以磅为单位）。  <br/> |**xdDesignWindow** 和 **xdEditorWindow** 类型  <br/> |
|[Left](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.Left.aspx) 属性  <br/> |长整型的读/写属性，用于指定 **Window** 对象所代表的窗口的水平位置（以磅为单位）。  <br/> |**xdDesignWindow** 和 **xdEditorWindow** 类型  <br/> |
|[MailEnvelope](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.MailEnvelope.aspx) 属性  <br/> |返回对 [MailEnvelopeObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.MailEnvelopeObject.aspx) 对象的引用。  <br/> |仅限于 **xdEditorWindow** 类型  <br/> |
|[TaskPanes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.TaskPanes.aspx) 属性  <br/> |返回对 [TaskPanesCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.TaskPanesCollection.aspx) 集合的引用。  <br/> |**xdDesignWindow** 和 **xdEditorWindow** 类型  <br/> |
|[Top](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.Top.aspx) 属性  <br/> |长整型的读/写属性，用于指定 **Window** 对象所代表的窗口的垂直位置（以磅为单位）。  <br/> |**xdDesignWindow** 和 **xdEditorWindow** 类型  <br/> |
|[WindowType](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.WindowType.aspx) 属性  <br/> |返回一个数字，基于 [XdWindowType](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XdWindowType.aspx) 枚举，表示窗口的类型。  <br/> |**xdDesignWindow** 和 **xdEditorWindow** 类型  <br/> |
|[Width](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.Width.aspx) 属性  <br/> |长整型的读/写属性，用于指定 **Window** 对象所代表的窗口的宽度（以磅为单位）。  <br/> |**xdDesignWindow** 和 **xdEditorWindow** 类型  <br/> |
|[WindowState](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.WindowState.aspx) 属性  <br/> |[XdWindowState](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XdWindowState.aspx) 类型的读/写属性，用于返回或设置 **Window** 对象所表示的窗口的状态。  <br/> |**xdDesignWindow** 和 **xdEditorWindow** 类型  <br/> |
|[XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Window2.XDocument.aspx) 属性  <br/> |返回对与窗口关联的 [_XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument.aspx) 对象的引用。  <br/> |仅限于 **xdEditorWindow** 类型  <br/> |
   
## <a name="using-the-windowscollection-and-window-interfaces"></a>使用 WindowsCollection 和 Window 接口

通过 **Application** 接口的 [Windows](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.Windows.aspx) 属性可以访问 [WindowsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) 接口。使用 **WindowsCollection** 接口访问表单的窗口时，将使用索引器（对于 Visual C#）或将一个长整型值传递给 **Item** 属性（对于 Visual Basic）以返回对 **WindowObject** 接口实例的引用。例如，如下代码设置对包含在 **WindowsCollection** 集合中的第一个 **WindowObject** 对象的引用。
  
```cs
WindowObject objWindow = thisApplication.Windows[0];
```

```vb
Dim objWindow As WindowObject = thisApplication.Windows(0)
```

但是，可以使用 [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.ActiveWindow.aspx) 接口的 **ActiveWindow** 属性直接访问当前打开的窗口，而无需通过 ** WindowsCollection **，如下面的代码所演示。
  
```cs
WindowObject objWindow = thisApplication.ActiveWindow;
```

```vb
Dim objWindow As WindowObject = thisApplication.ActiveWindow
```

> [!NOTE]
> 调试 InfoPath 托管代码项目时， **ActiveWindow** 属性总是返回 **null**，因为调试窗口是活动的。 
  
还可以使用与表单的基础 XML 文档关联的 **View** 接口的 [Window](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Window.aspx) 属性来访问 [WindowObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.aspx)。 **XDocument** 接口的 **View** 属性用来访问 **View** 对象。例如，下面的代码设置对与表单的基础 XML 文档的视图相关联的 **WindowObject** 对象的引用。 
  
```cs
WindowObject objWindow = thisXDocument.View.Window;
```

```vb
Dim objWindow As WindowObject = thisXDocument.View.Window
```

> [!NOTE]
> **Window** 对象的某些属性和方法只用于编辑窗口类型；如果用于设计窗口类型，它们将返回错误。本主题前面所显示的表中列出了每个窗口类型所支持的属性和方法。您可以在代码中使用 **WindowType** 属性来确定所使用的窗口的类型。 
  

