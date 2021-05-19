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
# <a name="respond-to-form-events-using-the-infopath-2003-object-model"></a><span data-ttu-id="f9bee-105">使用 InfoPath 2003 对象模型响应表单事件</span><span class="sxs-lookup"><span data-stu-id="f9bee-105">Respond to Form Events Using the InfoPath 2003 Object Model</span></span>

<span data-ttu-id="f9bee-p102">可以编写代码来响应用户填写表单时可能发生的各种事件。若要在 InfoPath 中处理事件，则应在 InfoPath Designer 中创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="f9bee-p102">You can write code to respond to various events that can occur as a user fills out a form. To work with events in InfoPath, you create event handlers in the InfoPath designer.</span></span>
  
<span data-ttu-id="f9bee-p103">应在 InfoPath Designer 中创建 InfoPath 事件处理程序，因为当使用 InfoPath 2003 兼容对象模型时，InfoPath 会自动添加正确的声明，并在表单的代码文件（FormCode.cs 或 FormCode.vb）中应用一个属性 ([InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx) ) 以标识和接收事件处理程序。创建事件处理程序后，不应在表单的代码文件中改变其声明和属性。</span><span class="sxs-lookup"><span data-stu-id="f9bee-p103">InfoPath event handlers should be created in the InfoPath designer because, when using the InfoPath 2003-compatible object model, InfoPath automatically adds the correct declaration and applies an attribute ([InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx) ) in a form's code file (FormCode.cs or FormCode.vb) to identify and sink the event handler. After you have created an event handler, you should not alter its declaration and attribute in the form's code file.</span></span> 
  
<span data-ttu-id="f9bee-110">有关创建 InfoPath 事件处理程序的信息，请参阅[使用 InfoPath 2003 对象模型添加事件处理程序](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="f9bee-110">For information about creating the InfoPath event handlers, see [Add an Event Handler Using the InfoPath 2003 Object Model](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md).</span></span>
  
## <a name="overview-of-the-event-objects"></a><span data-ttu-id="f9bee-111">事件对象概述</span><span class="sxs-lookup"><span data-stu-id="f9bee-111">Overview of the Event Objects</span></span>

<span data-ttu-id="f9bee-p104">InfoPath 2003 兼容对象模型实现了在 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间中公开的九个事件对象。下表列出了每个 InfoPath 事件对象以及与它们关联的事件处理程序，并描述了它们提供的功能。</span><span class="sxs-lookup"><span data-stu-id="f9bee-p104">The InfoPath 2003-compatible object model implements nine event objects that are exposed in the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace. The following table lists each of the InfoPath event objects, the event handlers they are associated with, and a description of the functionality they provide.</span></span> 
  
|<span data-ttu-id="f9bee-114">**名称**</span><span class="sxs-lookup"><span data-stu-id="f9bee-114">**Name**</span></span>|<span data-ttu-id="f9bee-115">**事件处理程序**</span><span class="sxs-lookup"><span data-stu-id="f9bee-115">**Event handlers**</span></span>|<span data-ttu-id="f9bee-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9bee-116">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f9bee-117">DataDOMEvent</span><span class="sxs-lookup"><span data-stu-id="f9bee-117">DataDOMEvent</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.aspx) <br/> |[<span data-ttu-id="f9bee-118">OnBeforeChange</span><span class="sxs-lookup"><span data-stu-id="f9bee-118">OnBeforeChange</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnBeforeChange.aspx) <br/> <span data-ttu-id="f9bee-119">[OnValidate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnValidate.aspx) 、 [OnAfterChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnAfterChange.aspx)</span><span class="sxs-lookup"><span data-stu-id="f9bee-119">[OnValidate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnValidate.aspx) , [OnAfterChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnAfterChange.aspx)</span></span> <br/> |<span data-ttu-id="f9bee-p105">返回在 XML 文档对象模型 (DOM) 更改期间对表单的基础 XML 文档的引用、返回状态以及包含关于 XML 节点信息的其他属性。还包括引发错误的方法。</span><span class="sxs-lookup"><span data-stu-id="f9bee-p105">Returns a reference to a form's underlying XML document, the return status, and other properties that contain information about the XML node during an XML Document Object Model (DOM) change. Also includes a method for raising an error.</span></span>  <br/> |
|[<span data-ttu-id="f9bee-122">DocActionEvent</span><span class="sxs-lookup"><span data-stu-id="f9bee-122">DocActionEvent</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DocActionEvent.aspx) <br/> |[<span data-ttu-id="f9bee-123">OnClick</span><span class="sxs-lookup"><span data-stu-id="f9bee-123">OnClick</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._ButtonEventSink_Event.OnClick.aspx) <br/> |<span data-ttu-id="f9bee-124">返回在表单区域内单击按钮期间对表单的基础 XML 文档的引用、返回状态以及源 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="f9bee-124">Returns a reference to a form's underlying XML document, the return status, and the source XML node during a button click in the form area.</span></span>  <br/> |
|[<span data-ttu-id="f9bee-125">DocContextChangeEvent</span><span class="sxs-lookup"><span data-stu-id="f9bee-125">DocContextChangeEvent</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DocContextChangeEvent.aspx) <br/> |[<span data-ttu-id="f9bee-126">OnContextChange</span><span class="sxs-lookup"><span data-stu-id="f9bee-126">OnContextChange</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnContextChange.aspx) <br/> |<span data-ttu-id="f9bee-127">返回有关 XML 文档对象模型 (DOM) 节点的信息，该节点是表单的基础 XML 文档的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="f9bee-127">Returns information about the XML Document Object Model (DOM) node that is the current context of the form's underlying XML document.</span></span>  <br/> |
|[<span data-ttu-id="f9bee-128">DocEvent</span><span class="sxs-lookup"><span data-stu-id="f9bee-128">DocEvent</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DocEvent.aspx) <br/> |<span data-ttu-id="f9bee-129">[OnSwitchView](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSwitchView.aspx) 、 [OnAfterImport](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnAfterImport.aspx)</span><span class="sxs-lookup"><span data-stu-id="f9bee-129">[OnSwitchView](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSwitchView.aspx) , [OnAfterImport](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnAfterImport.aspx)</span></span> <br/> |<span data-ttu-id="f9bee-130">返回在切换视图或表单合并操作期间对表单的基础 XML 文档的引用。</span><span class="sxs-lookup"><span data-stu-id="f9bee-130">Returns a reference to a form's underlying XML document during a switch view or form merge operation.</span></span>  <br/> |
|[<span data-ttu-id="f9bee-131">DocReturnEvent</span><span class="sxs-lookup"><span data-stu-id="f9bee-131">DocReturnEvent</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DocReturnEvent.aspx) <br/> |<span data-ttu-id="f9bee-132">[OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) 、 [OnSubmitRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSubmitRequest.aspx)</span><span class="sxs-lookup"><span data-stu-id="f9bee-132">[OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) , [OnSubmitRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSubmitRequest.aspx)</span></span> <br/> |<span data-ttu-id="f9bee-133">返回在加载或提交表单期间对表单的基础 XML 文档的引用和返回状态。</span><span class="sxs-lookup"><span data-stu-id="f9bee-133">Returns a reference to a form's underlying XML document and the return status during the loading or submission of a form.</span></span>  <br/> |
|[<span data-ttu-id="f9bee-134">MergeEvent</span><span class="sxs-lookup"><span data-stu-id="f9bee-134">MergeEvent</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.MergeEvent.aspx) <br/> |[<span data-ttu-id="f9bee-135">OnMergeRequest</span><span class="sxs-lookup"><span data-stu-id="f9bee-135">OnMergeRequest</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnMergeRequest.aspx) <br/> |<span data-ttu-id="f9bee-136">返回一些属性和方法，在 **OnMergeRequest** 事件期间，可以使用这些属性和方法以编程方式与表单的基础 XML 文档进行交互，并确定诸如合并的文件数等合并属性。</span><span class="sxs-lookup"><span data-stu-id="f9bee-136">Returns properties and methods that can be used during an **OnMergeRequest** event to programmatically interact with a form's underlying XML document and to determine merge properties such as the number of files being merged.</span></span>  <br/> |
|[<span data-ttu-id="f9bee-137">SaveEvent</span><span class="sxs-lookup"><span data-stu-id="f9bee-137">SaveEvent</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SaveEvent.aspx) <br/> |[<span data-ttu-id="f9bee-138">OnSaveRequest</span><span class="sxs-lookup"><span data-stu-id="f9bee-138">OnSaveRequest</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSaveRequest.aspx) <br/> |<span data-ttu-id="f9bee-139">返回许多属性和方法，从 **OnSaveRequest** 事件处理程序中执行保存操作期间，可以使用这些属性和方法，通过编程方式与表单的基础 XML 文档进行交互，确定保存属性并执行保存操作。</span><span class="sxs-lookup"><span data-stu-id="f9bee-139">Returns a number of properties and methods that can be used during a save operation from the **OnSaveRequest** event handler to programmatically interact with a form's underlying XML document, determine save properties, and perform the save operation.</span></span>  <br/> |
|[<span data-ttu-id="f9bee-140">SignEvent</span><span class="sxs-lookup"><span data-stu-id="f9bee-140">SignEvent</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SignEvent.aspx) <br/> |[<span data-ttu-id="f9bee-141">OnSign</span><span class="sxs-lookup"><span data-stu-id="f9bee-141">OnSign</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSign.aspx) <br/> |<span data-ttu-id="f9bee-142">用于将其他数据添加到数字签名。</span><span class="sxs-lookup"><span data-stu-id="f9bee-142">Used to add additional data to the digital signature.</span></span>  <br/> |
|[<span data-ttu-id="f9bee-143">VersionUpgradeEvent</span><span class="sxs-lookup"><span data-stu-id="f9bee-143">VersionUpgradeEvent</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.VersionUpgradeEvent.aspx) <br/> |[<span data-ttu-id="f9bee-144">OnVersionUpgrade</span><span class="sxs-lookup"><span data-stu-id="f9bee-144">OnVersionUpgrade</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnVersionUpgrade.aspx) <br/> |<span data-ttu-id="f9bee-145">返回在版本升级操作期间对表单的基础 XML 文档的引用、返回状态、以及文档和解决方案版本号。</span><span class="sxs-lookup"><span data-stu-id="f9bee-145">Returns a reference to a form's underlying XML document, the return status, and the document and solution version numbers during the version upgrade operation.</span></span>  <br/> |
   
## <a name="using-the-event-objects"></a><span data-ttu-id="f9bee-146">使用事件对象</span><span class="sxs-lookup"><span data-stu-id="f9bee-146">Using the Event Objects</span></span>

<span data-ttu-id="f9bee-p106">创建事件处理程序时，InfoPath 将在项目的表单代码文件（FormCode.cs 或 FormCode.vb）中创建事件处理程序的声明。在事件处理程序的声明中，InfoPath 使用 **e** 作为传递给事件处理程序的参数的名称。该参数包含与事件处理程序关联的事件对象。</span><span class="sxs-lookup"><span data-stu-id="f9bee-p106">When you create an event handler, InfoPath creates the event handler's declaration in the project's form code file (FormCode.cs or FormCode.vb). In the declaration of the event handler, InfoPath uses **e** as the name of the parameter that is passed to the event handler. This parameter contains the event object that is associated with the event handler.</span></span> 
  
<span data-ttu-id="f9bee-150">例如，在设计模式下为 **OnLoad** 事件创建事件处理程序（通过单击“开发工具”选项卡上的“OnLoad 事件”）时，InfoPath 会将接收 **DocReturnEvent** 对象的事件处理程序的声明添加到表单代码文件中，然后打开代码编辑器，以便您可以将代码添加到以下事件处理程序声明中。</span><span class="sxs-lookup"><span data-stu-id="f9bee-150">For example, when you create an event handler for the **OnLoad** event in design mode (by clicking **On Load Event** on the **Developer** tab), InfoPath adds the declaration for the event handler that receives the **DocReturnEvent** object to the form code file, and then opens the Code Editor so that you can add your code to the following event handler declaration.</span></span> 
  
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

<span data-ttu-id="f9bee-p107">为事件处理程序编写代码时，可以使用由通过 **e** 参数传递的事件对象实现的属性和方法。例如，在下列 **OnBeforeChange** 事件处理程序中， [DataDOMEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.NewValue.aspx) 事件对象的 **NewValue** 属性用来检查刚刚发生更改的域的值。如果该值为空，将使用 [DataDOMEvent](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.ReturnMessage.aspx) 事件对象的 **ReturnMessage** 属性通过对话框向用户显示错误消息，并将 [ReturnStatus](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.ReturnStatus.aspx) 属性设置为 **false**，这表示不应接受用户所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f9bee-p107">When writing code for an event handler, you can use the properties and methods implemented by the event object that is passed through the **e** parameter. For example, in the following **OnBeforeChange** event handler, the [NewValue](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.NewValue.aspx) property of the **DataDOMEvent** event object is used to check the value of the field that was just changed. If it is blank, the [ReturnMessage](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.ReturnMessage.aspx) property of the **DataDOMEvent** event object is used to display an error to the user in a dialog box, and the [ReturnStatus](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.ReturnStatus.aspx) property is set to **false**, indicating that the changes the user made should not be accepted.</span></span>
  
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
> <span data-ttu-id="f9bee-p108">InfoPath 2003 兼容对象模型中的每个 InfoPath 事件对象均实现不同的属性和方法。有关特殊事件对象的详细信息，请在前面所示的"事件对象"表格中单击适当的对象。</span><span class="sxs-lookup"><span data-stu-id="f9bee-p108">Each of the InfoPath event objects in the InfoPath 2003-compatible object model implements different properties and methods. For more information about a particular event object, click the appropriate object in the Event Objects table shown earlier.</span></span> 
  

