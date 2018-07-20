---
title: 响应表单事件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- 事件顺序 [infopath 207]，事件 [InfoPath 2007]，响应，事件 [InfoPath 2007]，顺序，InfoPath 2007，响应事件，EventArgs 类 [InfoPath 2007]
localization_priority: Normal
ms.assetid: 754db64b-179f-4385-8dd9-c20c9407b186
description: 可以编写代码来响应用户在填写表单时可能发生的各种事件。若要在 InfoPath 中处理事件，则应在设计模式下使用表单模板时添加事件处理程序。
ms.openlocfilehash: 7968837fe0ed524104111bc3f2960860af51c75a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774024"
---
# <a name="respond-to-form-events"></a>响应表单事件

可以编写代码来响应用户在填写表单时可能发生的各种事件。若要在 InfoPath 中处理事件，则应在设计模式下使用表单模板时添加事件处理程序。
  
应始终在设计模式下创建 InfoPath 事件处理程序，因为 InfoPath 会自动将用于接收事件的正确声明添加到 **InternalStartup** 方法中并将事件处理程序的代码框架插入到表单的代码文件（FormCode.cs 或 FormCode.vb）中。创建了事件处理程序后，则不应在表单的代码文件中改变其声明。 
  
有关创建 InfoPath 事件处理程序的信息，请参阅[添加事件处理程序](how-to-add-an-event-handler.md)。
  
## <a name="overview-of-the-event-classes"></a>事件类概述

[Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的 InfoPath 模型可实现三个类，这些类又实现可由表单模板业务逻辑引发并处理的 12 个事件。下表列出了每个 InfoPath 事件对象及其关联的事件，并对它们提供的功能进行了说明。 
  
|**名称**|**事件**|**说明**|
|:-----|:-----|:-----|
|[ButtonEvent](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ButtonEvent.aspx) <br/> |[Clicked](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ButtonEvent.Clicked.aspx) <br/> |**ButtonEvent** 类用于实现在点击表单上的 **Button** 控件时所引发的 **Clicked** 事件。  <br/> |
|[FormEvents](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.aspx) <br/> |[ContextChanged](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.ContextChanged.aspx) <br/> [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) <br/> [Merge](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Merge.aspx) <br/> [Save](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Save.aspx) <br/> [Sign](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Sign.aspx) <br/> [Submit](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Submit.aspx) <br/> [VersionUpgrade](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.VersionUpgrade.aspx) <br/> [ViewSwitched](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.ViewSwitched.aspx) <br/> |**FormEvents** 类实现特定于 InfoPath 表单模板本身的事件：  <br/> **ContextChanged** <br/> 在上下文节点更改之后发生。  <br/> **Loading** <br/> 在加载了表单模板之后、初始化任何视图之前发生。  <br/> **Merge** <br/> 在从用户界面上调用了“**合并表单**”命令时发生，或者在用 `/aggregate` 命令行开关启动 InfoPath 时发生。  <br/> **Save** <br/> 在从用户界面使用“**保存**”或“**保存为**”命令时发生，或者在使用 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 类的 [Save](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Save.aspx) 和 [SaveAs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.SaveAs.aspx) 方法时发生。  <br/> **Sign** <br/> 在选定一组要通过“**数字签名**”对话框进行签名的签名数据后发生。  <br/> **Submit** <br/> 在用户界面中使用“**提交**”命令时发生，或者在使用 **XmlForm** 类的 [Submit](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Submit.aspx) 方法时发生。  <br/> **VersionUpgrade** <br/> 在当前打开的表单的版本号小于该表单所基于的表单模板的版本号时发生。  <br/> **ViewSwitched** <br/> 在成功切换了表单视图之后发生。  <br/> |
|[XmlEvent](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEvent.aspx) <br/> |[Changed](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEvent.Changed.aspx) <br/> [Changing](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEvent.Changing.aspx) <br/> [Validating](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEvent.Validating.aspx) <br/> |实现由表单实例的基础 XML 文档中的数据更改所引发的事件：  <br/> **Changed** <br/> 在对表单的基础 XML 文档的更改已被接受以及 **Validating** 事件发生后发生。  <br/> **Changing** <br/> 在对表单的基础 XML 文档进行更改之后、更改被接受之前发生。  <br/> **Validating** <br/> 在对表单的基础 XML 文档的更改被接受之后、 **Changed** 事件发生之前发生。  <br/> **XmlEvent** 类还实现 [RaiseUndoRedoForChanged](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEvent.RaiseUndoRedoForChanged.aspx) 属性，该属性获取或设置一个值，指示当撤消或恢复操作发生时是否将引发 **Changed** 事件。  <br/> |
   
> [!NOTE]
>  [!注释] 当在表单的非空字段中进行更改时， **Changed** 和 **Changing** 事件仅激发一次，而在对非空字段进行更改时 InfoPath 2003 以及由 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间提供的 InfoPath 2003 兼容对象模型中的相应事件（ [OnBeforeChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnBeforeChange.aspx) 和 [OnAfterChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnAfterChange.aspx) ）将激发两次：一次在删除旧值时激发，一次在插入新值时激发。 
  
## <a name="overview-of-the-eventargs-classes"></a>EventArgs 类概述

对于上述 12 个事件的每一个事件，都有一个与之关联的 **EventArgs** 对象，该对象传递给该事件的事件处理程序，以便提供可在事件处理程序代码中使用的状态信息和其他功能。下表列出了 InfoPath 事件、与这些事件关联的 **EventArgs** 对象以及对该对象的属性和方法所提供的功能的简短说明。有关该对象的特定属性和方法的详细信息，请在表中单击 **EventArgs** 对象的名称，然后单击该主题中的"成员"链接。 
  
|"事件"|**EventsArgs 类**|**说明**|
|:-----|:-----|:-----|
|**Clicked** <br/> |[ClickedEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ClickedEventArgs.aspx) <br/> |获取控件 ID。  <br/> 获取 **XPathNavigator** 对象，该对象位于表单的包含 **Button** 控件的基础 XML 文档的最内层 XML 节点。  <br/> |
|**ContextChanged** <br/> |[ContextChangedEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ContextChangedEventArgs.aspx) <br/> |获取在事件发生时执行的上下文更改的类型。  <br/> 获取一个值，该值指示是否随着撤消或恢复某个操作而发生了上下文更改事件。  <br/> 获取一个对 **XPathNavigator** 的引用，它位于引发该事件的上下文节点处。  <br/> |
|**Loading** <br/> |[LoadingEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.LoadingEventArgs.aspx) <br/> |指定加载后要在其中打开表单的视图。  <br/> 获取一个对 **XmlFormCancelEventArgs** 对象的引用。  <br/> 获取一个 **IDictionary**，它包含使用  `/InputParameters` 命令行选项指定或使用用于打开表单的 URL 中的查询参数指定的所有输入参数。  <br/> |
|**Merge** <br/> |[MergeEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.MergeEventArgs.aspx) <br/> |获取一个对 **XmlFormCancelEventArgs** 对象的引用。  <br/> 获取合并操作中被合并的表单的数目。  <br/> 获取当前要合并的表单的索引（从 0 开始）。  <br/> 获取或设置与 **Cancel** 属性一起使用的值，该值决定了是仅取消当前表单，还是取消整个合并操作。  <br/> 获取一个 **XPathNavigator** 对象，该对象位于当前要合并的表单的基础 XML 文档的根节点处。  <br/> |
|**Save** <br/> |[SaveEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SaveEventArgs.aspx) <br/> |执行用户请求的保存操作。  <br/> 获取一个对可用来取消事件的 **SaveCancelEventArgs** 对象的引用。  <br/> 获取要在事件的事件处理程序中使用的文件名。  <br/> 获取一个值，该值指示是将保存操作作为"保存"操作还是"另存为"操作来执行。  <br/> |
|**Sign** <br/> |[SignEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SignEventArgs.aspx) <br/> |获取或设置是否要显示“**数字签名**”对话框。  <br/> 获取引发事件的可签名数据组。  <br/> |
|**Submit** <br/> |[SubmitEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SubmitEventArgs.aspx) <br/> |获取一个对用来取消事件的 **XmlFormCancelEventArgs** 对象的引用。  <br/> |
|**VersionUpgrade** <br/> |[VersionUpgradeEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.VersionUpgradeEventArgs.aspx) <br/> |获取一个对用来取消事件的 **XmlFormCancelEventArgs** 对象的引用。  <br/> 获取正在升级的表单文档的版本号。  <br/> 获取与正在升级的表单关联的表单模板的版本号。  <br/> |
|**ViewSwitched** <br/> |[ViewSwitchedEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewSwitchedEventArgs.aspx) <br/> |**ViewSwitchedEventArgs** 类不为从 **System.Object** 继承的事件之外的事件提供任何属性和方法。  <br/> |
|**Changed** <br/> |[XmlEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.aspx) <br/> |获取一个 **XPathExpression** 对象，该对象包含返回当前正在更改的节点的 XPath 表达式。  <br/> 获取正在更改的节点的新值。  <br/> 获取一个 **XPathNavigator** 对象，该对象指向正在删除的节点的父节点。  <br/> 获取正在更改的节点的原始值。  <br/> 获取一个 [XmlOperation](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlOperation.aspx) 枚举，该枚举指示更改节点后发生的操作的类型。  <br/> 获取一个 **XPathNavigator** 对象，该对象指向正在更改的节点。  <br/> 获取一个值，该值指示正在更改的节点是否是撤消操作或恢复操作的一部分。  <br/> |
|**Changing** <br/> |[XmlChangingEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlChangingEventArgs.aspx) <br/> |获取一个与该事件关联的 **XmlFormCancelEventArgs** 对象。  <br/> 继承上面列出的 **XmlEventArgs** 对象的所有功能。  <br/> |
|**Validating** <br/> |[XmlValidatingEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlValidatingEventArgs.aspx) <br/> |创建一个包含自定义错误信息及指定值的 [FormError](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.aspx) 对象，并将该对象添加到表单的 [FormErrorCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.aspx) 对象。  <br/> 继承上面列出的 **XmlEventArgs** 对象的所有功能。  <br/> |
   
## <a name="using-the-eventargs-objects"></a>使用 EventArgs 对象

创建事件处理程序时，InfoPath 将在项目的表单代码中创建事件处理程序的声明。在事件处理程序的声明中，InfoPath 使用 **e** 作为传递给事件处理程序的参数的名称。此参数包含与事件处理程序关联的 **EventArgs** 对象，以便在事件发生时提供状态信息和其他功能。 
  
例如，在设计模式下为 **Loading** 事件创建事件处理程序（通过单击“**开发工具**”选项卡上的“**Loading 事件**”菜单）时，InfoPath 会将接收 [LoadingEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.LoadingEventArgs.aspx) 对象的事件处理程序的声明添加到表单代码文件中，然后打开代码编辑器，以便能够将代码添加到以下事件处理程序声明中。 
  
```cs
public void FormEvents_Loading(object sender, LoadingEventArgs e)
{
   // Write your code here.
}
```

```vb
Public Sub FormEvents_Loading(ByVal sender As Object, _
   ByVal e As LoadingEventArgs)
   ' Write your code here.
End Sub
```

为事件处理程序编写代码时，可以使用通过 **e** 参数传递的 **EventArgs** 对象所实现的属性和方法。例如，在以下 **Changing** 事件处理程序中， [XmlChangingEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.NewValue.aspx) 对象（从 [XmlEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlChangingEventArgs.aspx) 类继承）的 [NewValue](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.aspx) 属性用于检查刚刚更改的字段的值。如果用户更改字段并将其保留为空，则会使用 [XmlChangingEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCancelEventArgs.Message.aspx) 对象的 [CancelableArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlFormCancelEventArgs.aspx) 属性来访问 [XmlFormCancelEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlChangingEventArgs.CancelableArgs.aspx) 类的 **Message** 属性以向用户显示错误，同时还会将 **XmlFormCancelEventArgs.Cancel** 属性设置为 **true** 以取消事件并回滚用户所做的更改。
  
```cs
public void field1_Changing(object sender, LoadingEventArgs e)
{
   // Determine whether there is a new value.
   if (e.NewValue == "")
   {
      // The value is blank, so display an error message
      // and roll back the changes.
      e.CancelableArgs.Message = 
         "You must supply a value for this field.";
      e.CancelableArgs.Cancel = true;
      return;
   }
}
```

```vb
Public Sub field1_Changing(ByVal sender As Object, _
   ByVal e As LoadingEventArgs)
   ' Determine whether there is a new value.
   If (e.NewValue = "") Then
      ' The value is blank, so display an error message 
      ' and roll back the changes.
      e.CancelableArgs.Message = _
         "You must supply a value for this field."
      e.CancelableArgs.Cancel = True
      Return
   End If
End Sub
```


