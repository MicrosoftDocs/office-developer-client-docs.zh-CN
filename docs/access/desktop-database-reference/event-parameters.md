---
title: 事件参数 （访问桌面数据库参考 （英文）
TOCTitle: Event Parameters
ms:assetid: 626de9b1-4d45-d77e-ccf2-23f2ea31c043
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249371(v=office.15)
ms:contentKeyID: 48545239
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 00258406ec48b6a4d2a3cf2691e7d54776d30fc9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465612"
---
# <a name="event-parameters"></a>事件参数


**适用于**： Access 2013 |Office 2013


每个事件处理程序都有一个状态参数，用于控制事件处理程序。对于 Complete 事件，此参数还用来指示生成该事件的操作是成功还是失败。大多数 Complete 事件还有一个错误参数，用于提供可能已发生的任何错误的相关信息，另外还有一个或多个对象参数，用于引用执行操作的 ADO 对象。例如，[ExecuteComplete](executecomplete-event-ado.md) 事件包括与事件关联的 **Command** 、 **Recordset** 和 **Connection** 对象的对象参数。在以下 Microsoft Visual Basic 示例中，您会看到 pCommand、pRecordset 和 pConnection 对象，这些对象代表 **Execute** 方法所使用的 **Command** 、 **Recordset** 和 **Connection** 对象。

```vb 
 
Private Sub connEvent_ExecuteComplete(ByVal RecordsAffected As Long, _ 
 ByVal pError As ADODB.Error, _ 
 adStatus As ADODB.EventStatusEnum, _ 
 ByVal pCommand As ADODB.Command, _ 
 ByVal pRecordset As ADODB.Recordset, _ 
 ByVal pConnection As ADODB.Connection) 
```

除 **Error** 对象以外，相同的参数将传递给 Will 事件。这将使您有机会检查要在挂起的操作中使用的每个对象，并确定是否应当允许操作完成。

某些事件处理程序有 *Reason* 参数，该参数可以提供有关事件发生原因的其他信息。例如，可以由于任何一个导航方法（**MoveNext**、**MovePrevious** 等）被调用或作为重新查询的结果而发生 **WillMove** 和 **MoveComplete** 事件。

## <a name="status-parameter"></a>状态参数

调用事件处理程序例程时，*Status* 参数将设置为下列值之一。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adStatusOK</strong></p></td>
<td><p>传递给 Will 和 Complete 事件。该值表示导致事件发生的操作已成功完成。</p></td>
</tr>
<tr class="even">
<td><p><strong>adStatusErrorsOccurred</strong></p></td>
<td><p>只传递给 Complete 事件。该值表示导致事件发生的操作不成功，或 Will 事件取消了操作。请检查 <em>Error</em> 参数，以获得更多详细信息。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adStatusCantDeny</strong></p></td>
<td><p>只传递给 Will 事件。该值表示 Will 事件无法取消操作。它必须执行。</p></td>
</tr>
</tbody>
</table>


如果决定在 Will 事件中应当继续执行操作，请保持 *Status* 参数不变。但是，只要传入的状态参数未设置为 **adStatusCantDeny**，就可以通过将 *Status* 更改为 **adStatusCancel** 来取消挂起的操作。这样做时，与操作关联的 Complete 事件会将它的 *Status* 参数设置为 **adStatusErrorsOccurred**。传递给 Complete 事件的 **Error** 对象将包含值 **adErrOperationCancelled**。

如果不想再处理事件，可以将 *Status* 设置为 **adStatusUnwantedEvent**，应用程序将不再接收事件通知。但请记住，某些事件可以由多个原因引发。在这种情况下，必须为每个可能的原因指定 **adStatusUnwantedEvent**。例如，对于 **adRsnAddNew**、**adRsnDelete**、**adRsnUpdate**、**adRsnUndoUpdate**、**adRsnUndoAddNew**、**adRsnUndoDelete** 和 **adRsnFirstChange**，当它们发生时，为了停止接收挂起的 **RecordChange** 事件的通知，必须将 *Status* 参数设置为 **adStatusUnwantedEvent**。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adStatusUnwantedEvent</strong></p></td>
<td><p>请求此事件处理程序不再接收进一步的通知。</p></td>
</tr>
<tr class="even">
<td><p><strong>adStatusCancel</strong></p></td>
<td><p>请求取消将要发生的操作。</p></td>
</tr>
</tbody>
</table>


## <a name="error-parameter"></a>Error 参数

*Error*参数是对 ADO[错误](error-object-ado.md)对象的引用。 *Status*参数设置为**adStatusErrorsOccurred**时, **Error**对象包含有关操作失败的原因的详细信息。 如果与 Complete 事件关联的将事件已通过*状态*参数设置为**adStatusCancel**取消该操作，error 对象始终设置为**adErrOperationCancelled**。

## <a name="object-parameter"></a>Object 参数

每个事件都会接收一个或多个对象，该（这些）对象代表操作所涉及的对象。例如， **ExecuteComplete** 事件会接收 **Command** 对象、 **Recordset** 对象和 **Connection** 对象。

## <a name="reason-parameter"></a>Reason 参数

*Reason* 参数 (*adReason*) 可提供有关事件发生的原因的其他信息。具有 *adReason* 参数的事件可能每次出于不同的原因而被调用几次（即使对于同一个操作）。例如，对于将要执行或撤消的插入、删除或修改记录的操作，会调用 **WillChangeRecord** 事件处理程序。如果希望只有当事件由于特定原因而发生时才处理该事件，则可以使用 *adReason* 参数来筛选掉您不感兴趣的事件。例如，如果希望只在由于添加记录而发生记录更改事件时才处理这些事件，则可以执行以下代码：

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

在这里，其他每个原因都可能导致通知发生。但是，对于每个原因只会发生一次通知。对于每个原因发生一次通知后，只有在添加新记录时，您才会收到通知。

相比之下，您需将*adStatus*设置为**adStatusUnwantedEvent**一次只能请求的事件处理程序没有**adReason**参数停止接收事件通知。

