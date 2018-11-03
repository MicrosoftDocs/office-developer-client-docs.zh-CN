---
title: 事件参数 （访问桌面数据库参考 （英文）
TOCTitle: Event parameters
ms:assetid: 626de9b1-4d45-d77e-ccf2-23f2ea31c043
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249371(v=office.15)
ms:contentKeyID: 48545239
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3acad111c3e1329f50c64f3f6fd6c5f7430e558d
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946739"
---
# <a name="event-parameters"></a><span data-ttu-id="e75af-102">事件参数</span><span class="sxs-lookup"><span data-stu-id="e75af-102">Event parameters</span></span>

<span data-ttu-id="e75af-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e75af-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e75af-p101">每个事件处理程序都有一个状态参数，用于控制事件处理程序。对于 Complete 事件，此参数还用来指示生成该事件的操作是成功还是失败。大多数 Complete 事件还有一个错误参数，用于提供可能已发生的任何错误的相关信息，另外还有一个或多个对象参数，用于引用执行操作的 ADO 对象。例如，[ExecuteComplete](executecomplete-event-ado.md) 事件包括与事件关联的 **Command** 、 **Recordset** 和 **Connection** 对象的对象参数。在以下 Microsoft Visual Basic 示例中，您会看到 pCommand、pRecordset 和 pConnection 对象，这些对象代表 **Execute** 方法所使用的 **Command** 、 **Recordset** 和 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="e75af-p101">Every event handler has a status parameter that controls the event handler. For Complete events, this parameter is also used to indicate the success or failure of the operation that generated the event. Most Complete events also have an error parameter to provide information about any error that might have occurred, as well as one or more object parameters that refer to the ADO objects used to perform the operation. For example, the [ExecuteComplete](executecomplete-event-ado.md) event includes object parameters for the **Command**, **Recordset**, and **Connection** objects associated with the event. In the following Microsoft Visual Basic example, you can see the pCommand, pRecordset and pConnection objects which represent the **Command**, **Recordset**, and **Connection** objects used by the **Execute** method.</span></span>

```vb 
 
Private Sub connEvent_ExecuteComplete(ByVal RecordsAffected As Long, _ 
 ByVal pError As ADODB.Error, _ 
 adStatus As ADODB.EventStatusEnum, _ 
 ByVal pCommand As ADODB.Command, _ 
 ByVal pRecordset As ADODB.Recordset, _ 
 ByVal pConnection As ADODB.Connection) 
```

<span data-ttu-id="e75af-p102">除 **Error** 对象以外，相同的参数将传递给 Will 事件。这将使您有机会检查要在挂起的操作中使用的每个对象，并确定是否应当允许操作完成。</span><span class="sxs-lookup"><span data-stu-id="e75af-p102">Except for the **Error** object, the same parameters are passed to the Will events. This gives you the opportunity to examine each of the objects to be used in the pending operation and determine whether the operation should be allowed to complete.</span></span>

<span data-ttu-id="e75af-p103">某些事件处理程序有 *Reason* 参数，该参数可以提供有关事件发生原因的其他信息。例如，可以由于任何一个导航方法（**MoveNext**、**MovePrevious** 等）被调用或作为重新查询的结果而发生 **WillMove** 和 **MoveComplete** 事件。</span><span class="sxs-lookup"><span data-stu-id="e75af-p103">Some event handlers have a *Reason* parameter, which provides additional information about why the event occurred. For example, the **WillMove** and **MoveComplete** events can occur due to any one of the navigation methods (**MoveNext**, **MovePrevious**, and so on) being called or as the result of a requery.</span></span>

## <a name="status-parameter"></a><span data-ttu-id="e75af-113">状态参数</span><span class="sxs-lookup"><span data-stu-id="e75af-113">Status Parameter</span></span>

<span data-ttu-id="e75af-114">调用事件处理程序例程时，*Status* 参数将设置为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="e75af-114">When the event-handler routine is called, the *Status* parameter is set to one of the following values.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e75af-115">值</span><span class="sxs-lookup"><span data-stu-id="e75af-115">Value</span></span></p></th>
<th><p><span data-ttu-id="e75af-116">说明</span><span class="sxs-lookup"><span data-stu-id="e75af-116">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e75af-117"><strong>adStatusOK</strong></span><span class="sxs-lookup"><span data-stu-id="e75af-117"><strong>adStatusOK</strong></span></span></p></td>
<td><p><span data-ttu-id="e75af-p104">传递给 Will 和 Complete 事件。该值表示导致事件发生的操作已成功完成。</span><span class="sxs-lookup"><span data-stu-id="e75af-p104">Passed to both Will and Complete events. This value means that the operation that caused the event completed successfully.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e75af-120"><strong>adStatusErrorsOccurred</strong></span><span class="sxs-lookup"><span data-stu-id="e75af-120"><strong>adStatusErrorsOccurred</strong></span></span></p></td>
<td><p><span data-ttu-id="e75af-p105">只传递给 Complete 事件。该值表示导致事件发生的操作不成功，或 Will 事件取消了操作。请检查 <em>Error</em> 参数，以获得更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="e75af-p105">Passed to Complete events only. This value means that the operation that caused the event was unsuccessful, or a Will event canceled the operation. Check the <em>Error</em> parameter for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e75af-124"><strong>adStatusCantDeny</strong></span><span class="sxs-lookup"><span data-stu-id="e75af-124"><strong>adStatusCantDeny</strong></span></span></p></td>
<td><p><span data-ttu-id="e75af-p106">只传递给 Will 事件。该值表示 Will 事件无法取消操作。它必须执行。</span><span class="sxs-lookup"><span data-stu-id="e75af-p106">Passed to Will events only. This value means that the operation cannot be canceled by the Will event. It must be performed.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e75af-p107">如果决定在 Will 事件中应当继续执行操作，请保持 *Status* 参数不变。但是，只要传入的状态参数未设置为 **adStatusCantDeny**，就可以通过将 *Status* 更改为 **adStatusCancel** 来取消挂起的操作。这样做时，与操作关联的 Complete 事件会将它的 *Status* 参数设置为 **adStatusErrorsOccurred**。传递给 Complete 事件的 **Error** 对象将包含值 **adErrOperationCancelled**。</span><span class="sxs-lookup"><span data-stu-id="e75af-p107">If you determine in your Will event that the operation should continue, leave the *Status* parameter unchanged. As long as the incoming status parameter was not set to **adStatusCantDeny**, however, you can cancel the pending operation by changing *Status* to **adStatusCancel**. When you do so, the Complete event associated with the operation has its *Status* parameter set to **adStatusErrorsOccurred**. The **Error** object passed to the Complete event will contain the value **adErrOperationCancelled**.</span></span>

<span data-ttu-id="e75af-p108">如果不想再处理事件，可以将 *Status* 设置为 **adStatusUnwantedEvent**，应用程序将不再接收事件通知。但请记住，某些事件可以由多个原因引发。在这种情况下，必须为每个可能的原因指定 **adStatusUnwantedEvent**。例如，对于 **adRsnAddNew**、**adRsnDelete**、**adRsnUpdate**、**adRsnUndoUpdate**、**adRsnUndoAddNew**、**adRsnUndoDelete** 和 **adRsnFirstChange**，当它们发生时，为了停止接收挂起的 **RecordChange** 事件的通知，必须将 *Status* 参数设置为 **adStatusUnwantedEvent**。</span><span class="sxs-lookup"><span data-stu-id="e75af-p108">If you no longer want to process an event, you can set *Status* to **adStatusUnwantedEvent** and your application will no longer receive notification of that event. Remember, however, that some events can be raised for more than one reason. In that case, you must specify **adStatusUnwantedEvent** for each possible reason. For example, in order to stop receiving notification of pending **RecordChange** events, you must set the *Status* parameter to **adStatusUnwantedEvent** for **adRsnAddNew**, **adRsnDelete**, **adRsnUpdate**, **adRsnUndoUpdate**, **adRsnUndoAddNew**, **adRsnUndoDelete**, and **adRsnFirstChange** as they occur.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e75af-136">值</span><span class="sxs-lookup"><span data-stu-id="e75af-136">Value</span></span></p></th>
<th><p><span data-ttu-id="e75af-137">说明</span><span class="sxs-lookup"><span data-stu-id="e75af-137">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e75af-138"><strong>adStatusUnwantedEvent</strong></span><span class="sxs-lookup"><span data-stu-id="e75af-138"><strong>adStatusUnwantedEvent</strong></span></span></p></td>
<td><p><span data-ttu-id="e75af-139">请求此事件处理程序不再接收进一步的通知。</span><span class="sxs-lookup"><span data-stu-id="e75af-139">Request that this event handler receive no further notifications.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e75af-140"><strong>adStatusCancel</strong></span><span class="sxs-lookup"><span data-stu-id="e75af-140"><strong>adStatusCancel</strong></span></span></p></td>
<td><p><span data-ttu-id="e75af-141">请求取消将要发生的操作。</span><span class="sxs-lookup"><span data-stu-id="e75af-141">Request cancellation of the operation that is about to occur.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="error-parameter"></a><span data-ttu-id="e75af-142">Error 参数</span><span class="sxs-lookup"><span data-stu-id="e75af-142">Error Parameter</span></span>

<span data-ttu-id="e75af-143">*Error*参数是对 ADO[错误](error-object-ado.md)对象的引用。</span><span class="sxs-lookup"><span data-stu-id="e75af-143">The *Error* parameter is a reference to an ADO [Error](error-object-ado.md) object.</span></span> <span data-ttu-id="e75af-144">*Status*参数设置为**adStatusErrorsOccurred**时, **Error**对象包含有关操作失败的原因的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e75af-144">When the *Status* parameter is set to **adStatusErrorsOccurred**, the **Error** object contains details about why the operation failed.</span></span> <span data-ttu-id="e75af-145">如果与 Complete 事件关联的将事件已通过*状态*参数设置为**adStatusCancel**取消该操作，error 对象始终设置为**adErrOperationCancelled**。</span><span class="sxs-lookup"><span data-stu-id="e75af-145">If the Will event associated with a Complete event has canceled the operation by setting the *Status* parameter to **adStatusCancel**, the error object is always set to **adErrOperationCancelled**.</span></span>

## <a name="object-parameter"></a><span data-ttu-id="e75af-146">Object 参数</span><span class="sxs-lookup"><span data-stu-id="e75af-146">Object Parameter</span></span>

<span data-ttu-id="e75af-p110">每个事件都会接收一个或多个对象，该（这些）对象代表操作所涉及的对象。例如， **ExecuteComplete** 事件会接收 **Command** 对象、 **Recordset** 对象和 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="e75af-p110">Each event receives one or more objects representing the objects that are involved in the operation. For example, the **ExecuteComplete** event receives a **Command** object, a **Recordset** object, and a **Connection** object.</span></span>

## <a name="reason-parameter"></a><span data-ttu-id="e75af-149">Reason 参数</span><span class="sxs-lookup"><span data-stu-id="e75af-149">Reason Parameter</span></span>

<span data-ttu-id="e75af-p111">*Reason* 参数 (*adReason*) 可提供有关事件发生的原因的其他信息。具有 *adReason* 参数的事件可能每次出于不同的原因而被调用几次（即使对于同一个操作）。例如，对于将要执行或撤消的插入、删除或修改记录的操作，会调用 **WillChangeRecord** 事件处理程序。如果希望只有当事件由于特定原因而发生时才处理该事件，则可以使用 *adReason* 参数来筛选掉您不感兴趣的事件。例如，如果希望只在由于添加记录而发生记录更改事件时才处理这些事件，则可以执行以下代码：</span><span class="sxs-lookup"><span data-stu-id="e75af-p111">The *Reason* parameter, *adReason*, provides additional information about why the event occurred. Events with an *adReason* parameter may be called several times, even for the same operation, each time for a different reason. For example, the **WillChangeRecord** event handler is called for operations that are about to do or undo the insertion, deletion, or modification of a record. If you want to process an event only when it occurs for a particular reason, you can use the *adReason* parameter to filter out the occurrences you are not interested in. For example, if you wanted to process record-change events only when they occur because a record was added, you can do something like this:</span></span>

```vb 
 
' BeginEventExampleVB01 
Private Sub rsTest_WillChangeRecord(ByVal adReason As ADODB.EventReasonEnum, ByVal cRecords As Long, adStatus As ADODB.EventStatusEnum, ByVal pRecordset As ADODB.Recordset) 
 If adReason = adRsnAddNew Then 
 ' Process event 
 '... 
 Else 
 ' Cancel event notification for all 
 ' other possible adReason values. 
 adStatus = adStatusUnwantedEvent 
 End If 
End Sub 
' EndEventExampleVB01 
```

<span data-ttu-id="e75af-p112">在这里，其他每个原因都可能导致通知发生。但是，对于每个原因只会发生一次通知。对于每个原因发生一次通知后，只有在添加新记录时，您才会收到通知。</span><span class="sxs-lookup"><span data-stu-id="e75af-p112">In this case, notification can potentially occur for each of the other reasons. However, it will occur only once for each reason. After the notification has occurred once for each reason, you will receive notification only for the addition of a new record.</span></span>

<span data-ttu-id="e75af-158">相比之下，您需将*adStatus*设置为**adStatusUnwantedEvent**一次只能请求的事件处理程序没有**adReason**参数停止接收事件通知。</span><span class="sxs-lookup"><span data-stu-id="e75af-158">In contrast, you need to set *adStatus* to **adStatusUnwantedEvent** only one time to request that an event handler without an **adReason** parameter stop receiving event notifications.</span></span>

