---
title: 使用 InfoPath 2003 对象模型响应表单事件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- form templates [infopath 2007], responding to events,InfoPath 2003-compatible form templates, responding to form events
localization_priority: Normal
ms.assetid: 59e9c1ed-32a8-4bcd-bdfc-9aa568a34d2a
description: 可以编写代码来响应用户填写表单时可能发生的各种事件。若要在 InfoPath 中处理事件，则应在 InfoPath Designer 中创建事件处理程序。
ms.openlocfilehash: b7347f882df991e64bdf4e76c471b1220a84dc58
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433491"
---
# <a name="respond-to-form-events-using-the-infopath-2003-object-model"></a>使用 InfoPath 2003 对象模型响应表单事件

可以编写代码来响应用户填写表单时可能发生的各种事件。若要在 InfoPath 中处理事件，则应在 InfoPath Designer 中创建事件处理程序。
  
应在 InfoPath Designer 中创建 InfoPath 事件处理程序，因为当使用 InfoPath 2003 兼容对象模型时，InfoPath 会自动添加正确的声明，并在表单的代码文件（FormCode.cs 或 FormCode.vb）中应用一个属性 ([InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx) ) 以标识和接收事件处理程序。创建事件处理程序后，不应在表单的代码文件中改变其声明和属性。 
  
有关创建 InfoPath 事件处理程序的信息，请参阅[使用 InfoPath 2003 对象模型添加事件处理程序](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)。
  
## <a name="overview-of-the-event-objects"></a>事件对象概述

InfoPath 2003 兼容对象模型实现了在 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间中公开的九个事件对象。下表列出了每个 InfoPath 事件对象以及与它们关联的事件处理程序，并描述了它们提供的功能。 
  
|**名称**|**事件处理程序**|**说明**|
|:-----|:-----|:-----|
|[DataDOMEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.aspx) <br/> |[OnBeforeChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnBeforeChange.aspx) <br/> [OnValidate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnValidate.aspx) 、 [OnAfterChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnAfterChange.aspx) <br/> |返回在 XML 文档对象模型 (DOM) 更改期间对表单的基础 XML 文档的引用、返回状态以及包含关于 XML 节点信息的其他属性。还包括引发错误的方法。  <br/> |
|[DocActionEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DocActionEvent.aspx) <br/> |[OnClick](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._ButtonEventSink_Event.OnClick.aspx) <br/> |返回在表单区域内单击按钮期间对表单的基础 XML 文档的引用、返回状态以及源 XML 节点。  <br/> |
|[DocContextChangeEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DocContextChangeEvent.aspx) <br/> |[OnContextChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnContextChange.aspx) <br/> |返回有关 XML 文档对象模型 (DOM) 节点的信息，该节点是表单的基础 XML 文档的当前上下文。  <br/> |
|[DocEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DocEvent.aspx) <br/> |[OnSwitchView](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSwitchView.aspx) 、 [OnAfterImport](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnAfterImport.aspx) <br/> |返回在切换视图或表单合并操作期间对表单的基础 XML 文档的引用。  <br/> |
|[DocReturnEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DocReturnEvent.aspx) <br/> |[OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) 、 [OnSubmitRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSubmitRequest.aspx) <br/> |返回在加载或提交表单期间对表单的基础 XML 文档的引用和返回状态。  <br/> |
|[MergeEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.MergeEvent.aspx) <br/> |[OnMergeRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnMergeRequest.aspx) <br/> |返回一些属性和方法，在 **OnMergeRequest** 事件期间，可以使用这些属性和方法以编程方式与表单的基础 XML 文档进行交互，并确定诸如合并的文件数等合并属性。  <br/> |
|[SaveEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SaveEvent.aspx) <br/> |[OnSaveRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSaveRequest.aspx) <br/> |返回许多属性和方法，从 **OnSaveRequest** 事件处理程序中执行保存操作期间，可以使用这些属性和方法，通过编程方式与表单的基础 XML 文档进行交互，确定保存属性并执行保存操作。  <br/> |
|[SignEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignEvent.aspx) <br/> |[OnSign](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSign.aspx) <br/> |用于将其他数据添加到数字签名。  <br/> |
|[VersionUpgradeEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.VersionUpgradeEvent.aspx) <br/> |[OnVersionUpgrade](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnVersionUpgrade.aspx) <br/> |返回在版本升级操作期间对表单的基础 XML 文档的引用、返回状态、以及文档和解决方案版本号。  <br/> |
   
## <a name="using-the-event-objects"></a>使用事件对象

创建事件处理程序时，InfoPath 将在项目的表单代码文件（FormCode.cs 或 FormCode.vb）中创建事件处理程序的声明。在事件处理程序的声明中，InfoPath 使用 **e** 作为传递给事件处理程序的参数的名称。该参数包含与事件处理程序关联的事件对象。 
  
例如，在设计模式下为 **OnLoad** 事件创建事件处理程序（通过单击“开发工具”选项卡上的“OnLoad 事件”）时，InfoPath 会将接收 **DocReturnEvent** 对象的事件处理程序的声明添加到表单代码文件中，然后打开代码编辑器，以便您可以将代码添加到以下事件处理程序声明中。 
  
```cs
// The following function handler is created by Microsoft Office 
// InfoPath. Do not modify the type or number of arguments.
[InfoPathEventHandler(EventType=InfoPathEventType.OnLoad)]
public void FormEvents_OnLoad(DocReturnEvent e)
{
   // Write your code here.
}
```

```vb
' The following function handler is created by Microsoft Office 
' InfoPath. Do not modify the type or number of arguments.
<InfoPathEventHandler(EventType:=InfoPathEventType.OnLoad)> _
Public Sub FormEvents_OnLoad(ByVal e As DocReturnEvent)
   ' Write your code here.
End Sub
```

为事件处理程序编写代码时，可以使用由通过 **e** 参数传递的事件对象实现的属性和方法。例如，在下列 **OnBeforeChange** 事件处理程序中， [DataDOMEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.NewValue.aspx) 事件对象的 **NewValue** 属性用来检查刚刚发生更改的域的值。如果该值为空，将使用 [DataDOMEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.ReturnMessage.aspx) 事件对象的 **ReturnMessage** 属性通过对话框向用户显示错误消息，并将 [ReturnStatus](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.ReturnStatus.aspx) 属性设置为 **false**，这表示不应接受用户所做的更改。
  
```cs
[InfoPathEventHandler(MatchPath="/my:myFields/my:field1", 
    EventType=InfoPathEventType.OnBeforeChange)]
public void field1_OnBeforeChange(DataDOMEvent e)
{
   // Determine whether there is a new value.
   if ((string)e.NewValue == "")
   {
      // The value is blank, so display an error message and roll
      // back the changes.
      e.ReturnMessage = "You must supply a value for this field.";
      e.ReturnStatus = false;
      return;
   }
}
```

```vb
<InfoPathEventHandler(MatchPath:="/my:myFields/my:field1", _ EventType:=InfoPathEventType.OnBeforeChange)> _
Public Sub field1_OnBeforeChange(ByVal e As DataDOMEvent)
   ' Determine whether there is a new value.
   If (e.NewValue = "") Then
      ' The value is blank, so display an error message and roll back
      ' the changes.
      e.ReturnMessage = "You must supply a value for this field."
      e.ReturnStatus = False
      Return
   End If
End Sub
```

> [!NOTE]
> InfoPath 2003 兼容对象模型中的每个 InfoPath 事件对象均实现不同的属性和方法。有关特殊事件对象的详细信息，请在前面所示的"事件对象"表格中单击适当的对象。 
  

