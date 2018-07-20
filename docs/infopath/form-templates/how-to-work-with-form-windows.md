---
title: 使用表单窗口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- windowscollection [infopath 2007],form windows [InfoPath 2007],Window class [InfoPath 2007]
localization_priority: Normal
ms.assetid: 32ae2427-882b-45f8-8754-0e8c27fc23ba
description: 以编程方式处理 InfoPath 表单时，您可以编写代码来访问该表单的窗口，然后自定义窗口中包含的某些项目。由 Microsoft.Office.InfoPath 命名空间提供的 InfoPath 对象模型通过结合使用 Window 类和 WindowCollection 类来支持对表单窗口进行访问。
ms.openlocfilehash: 5b24798e92849a2d79bf836e12dd91845ee58942
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774010"
---
# <a name="work-with-form-windows"></a>使用表单窗口

以编程方式处理 InfoPath 表单时，您可以编写代码来访问该表单的窗口，然后自定义窗口中包含的某些项目。由 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的 InfoPath 对象模型通过结合使用 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 类和 [WindowCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WindowCollection.aspx) 类来支持对表单窗口进行访问。 
  
> [!NOTE]
> 仅当使用“InfoPath 编辑器表单”**** 时，用于使用表单窗口的类才可用。 如果表单模板的****“兼容性”设置是****“Web 浏览器表单”，则这些类不可用。 
  
InfoPath 中有两类窗口： 
  
- 用户填写表单时所使用的编辑窗口。
    
- 用户设计表单模板时所使用的设计窗口。
    
编写表单模板中的代码时，编辑窗口提供了最有用的功能，因为您可以使用表示当前窗口的 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 对象来访问可以用来自定义表单编辑过程的各个属性和方法。 
  
## <a name="overview-of-the-windowscollection-class"></a>WindowsCollection 类概述

[WindowCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WindowCollection.aspx) 类提供了下列属性，表单模板开发人员可以使用这些属性来管理表单模板所包含的 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 对象。 
  
|**名称**|**说明**|
|:-----|:-----|
|[Count](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WindowCollection.Count.aspx) 属性  <br/> |获取集合中包含的 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 对象的数目。  <br/> |
|[Item](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WindowCollection.Item.aspx) 属性  <br/> |获取对指定的 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 对象的引用。  <br/> |
   
## <a name="overview-of-the-window-class"></a>Window 类概述

[Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 类提供下列方法和属性，表单开发人员可利用这些方法和属性与 InfoPath 窗口进行交互。 根据所使用的窗口类型 ([WindowType](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WindowType.aspx)) 的不同，对这些方法和属性的支持也不同。 有些方法和属性只适用于编辑器窗口类型 (**WindowType.Editor**)。 有些方法和属性既适用于编辑器窗口类型，也适用于设计器窗口类型 (**WindowType.Designer**)。 此外，与所有 InfoPath 对象模型成员一样，当从表单模板调用时，根据安全级别和表单部署方式的不同，对方法和属性的支持也有所不同。
  
|**名称**|**说明**|**窗口类型支持**|
|:-----|:-----|:-----|
|[Activate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.Activate.aspx) 方法  <br/> |激活窗口（将焦点移到该窗口）。  <br/> |**Designer** 和 **Editor** 类型  <br/> |
|[Active](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.Active.aspx) 属性  <br/> |获取 **Boolean** 值，指示窗口是否是当前的活动窗口。  <br/> |**Designer** 和 **Editor** 类型  <br/> |
|[Caption](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.Caption.aspx) 属性  <br/> |获取或设置由 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 对象表示的窗口的标题文本。  <br/> |仅限于 **Editor** 类型  <br/> |
|[Close()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.Close.aspx) 方法  <br/> |关闭窗口并提示保存对任何未保存表单所做的更改，或保存包含未保存更改的表单。  <br/> |仅限于 **Editor** 类型  <br/> |
|[Close(Boolean)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.Close.aspx) 方法  <br/> |关闭窗口并可以选择强制关闭未保存的表单或包含未保存的更改的表单，而不提示保存表单。  <br/> |仅限于 **Editor** 类型  <br/> |
|[CommandBars](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.CommandBars.aspx) 属性  <br/> |获取对与窗口关联的 Microsoft Office **CommandBars** 集合的引用。  <br/> |**Designer** 和 **Editor** 类型  <br/> |
|[Height](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.Height.aspx) 属性  <br/> |获取或设置窗口的高度（以磅为单位）。  <br/> |**Designer** 和 **Editor** 类型  <br/> |
|[Left](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.Left.aspx) 属性  <br/> |获取或设置窗口的水平位置，以磅为单位。  <br/> |**Designer** 和 **Editor** 类型  <br/> |
|[MailEnvelope](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.MailEnvelope.aspx) 属性  <br/> |获取对 [MailEnvelope](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.MailEnvelope.aspx) 类的引用。  <br/> |仅限于 **Editor** 类型  <br/> |
|[TaskPanes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.TaskPanes.aspx) 属性  <br/> |获取对 [TaskPaneCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.TaskPaneCollection.aspx) 集合的引用。  <br/> |**Designer** 和 **Editor** 类型  <br/> |
|[Top](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.Top.aspx) 属性  <br/> |获取或设置窗口的垂直位置，以磅为单位。  <br/> |**Designer** 和 **Editor** 类型  <br/> |
|[Width](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.Width.aspx) 属性  <br/> |获取或设置窗口的宽度，以磅为单位。  <br/> |**Designer** 和 **Editor** 类型  <br/> |
|[WindowState](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.WindowState.aspx) 属性  <br/> |获取窗口的状态或将窗口的状态设为 [WindowState](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WindowState.aspx) 值。  <br/> |**Designer** 和 **Editor** 类型  <br/> |
|[WindowType](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.WindowType.aspx) 属性  <br/> |获取窗口的类型并将它作为一个 [WindowType](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WindowType.aspx) 枚举值。  <br/> |**Designer** 和 **Editor** 类型  <br/> |
|[XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.XmlForm.aspx) 属性  <br/> |返回对与窗口关联的 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 对象的引用。  <br/> |仅限于 **Editor** 类型  <br/> |
   
## <a name="using-the-windowscollection-and-window-classes"></a>使用 WindowsCollection 和 Window 类

通过 [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WindowCollection.aspx) 类的 [Windows](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.Windows.aspx) 属性可以访问 [WindowCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 类。使用 [WindowCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WindowCollection.aspx) 类访问表单的窗口时，应使用索引器（对于 Visual C#）或将一个长整型值传递给 **Item** 属性（对于 Visual Basic）来返回对 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 对象实例的引用。例如，以下代码设置对包含在当前 InfoPath 会话的 [WindowCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 中的第一个 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WindowCollection.aspx) 对象的引用。 
  
```cs
Window myWindow = this.Application.Windows[0];
```

```vb
Dim myWindow As Window = Me.Application.Windows(0)
```

您可以直接使用 [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.ActiveWindow.aspx) 类的 [ActiveWindow](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 属性访问当前打开的窗口，而无需逐个访问 [WindowCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WindowCollection.aspx) ，如以下代码行所示。 
  
```cs
Window myWindow = this.Application.ActiveWindow;
```

```vb
Dim myWindow As Window = Me.Application.ActiveWindow
```

还可以通过使用 [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 类（表示正用于处理表单的基础 XML 文档的当前视图）的 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.Window.aspx) 属性来访问 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 对象。 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.CurrentView.aspx) 类的 [CurrentView](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 属性用于访问表示当前视图的 [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 对象。例如，以下代码可设置对与当前视图关联的 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 的引用。 
  
```cs
Window myWindow = this.CurrentView.Window;
```

```vb
Dim myWindow As Window = Me.CurrentView.Window
```

> [!NOTE]
> [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 类的某些属性和方法只适用于编辑窗口类型；如果用于设计窗口类型，它们将返回错误。本主题前面的表中列出了每种窗口类型所支持的属性和方法。您可以在代码中使用 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 属性来确定所使用的窗口的类型。 
  

