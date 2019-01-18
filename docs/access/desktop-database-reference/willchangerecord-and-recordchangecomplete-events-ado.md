---
title: WillChangeRecord 和 RecordChangeComplete 事件 (ADO)
TOCTitle: WillChangeRecord and RecordChangeComplete events (ADO)
ms:assetid: b21229b2-74e6-0798-95bf-0252f041831c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249851(v=office.15)
ms:contentKeyID: 48547162
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0113a7b22d0bba8e843ce9583e93eef848f872a5
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710837"
---
# <a name="willchangerecord-and-recordchangecomplete-events-ado"></a>WillChangeRecord 和 RecordChangeComplete 事件 (ADO)

**适用于**： Access 2013、 Office 2013

**WillChangeRecord** 事件在 [Recordset](recordset-object-ado.md) 中的一个或多个记录（行）发生更改之前调用。 **RecordChangeComplete** 事件在一个或多个记录发生更改之后调用。

## <a name="syntax"></a>语法

WillChangeRecord*adReason* *cRecords*、 *adStatus*、 *pRecordset*

RecordChangeComplete*adReason*、 *cRecords*、 *pError*、 *adStatus*、 *pRecordset*

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*adReason* |指定此事件原因的 [EventReasonEnum](eventreasonenum.md) 值。其值可以是 **adRsnAddNew** 、 **adRsnDelete** 、 **adRsnUpdate** 、 **adRsnUndoUpdate** 、 **adRsnUndoAddNew** 、 **adRsnUndoDelete** 或 **adRsnFirstChange** 。|
|*cRecords* |**长整型** 值，指定记录更改（受影响）的数量。|
|*pError* |[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。|
|*adStatus* |[EventStatusEnum](eventstatusenum.md)。 当调用**WillChangeRecord**时，此参数设置为**adStatusOK**如果导致事件的操作成功。 如果此事件不能请求取消挂起的操作，它是设置为**adStatusCantDeny** 。 <br/><br/>调用 **RecordChangeComplete** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果导致事件的操作失败，则该参数设置为 **adStatusErrorsOccurred** 。 <br/><br/>在 **WillChangeRecord** 返回之前，将该参数设置为 **adStatusCancel** 可以请求取消导致该事件的操作，将该参数设置为 adStatusUnwantedEvent 可以阻止随后进行通知。 <br/><br/>在 **RecordChangeComplete** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。|
|*pRecordset* |**Recordset** 对象。发生此事件的 **Recordset** 。|

## <a name="remarks"></a>备注

由于以下 **Recordset** 操作，行中第一个发生更改的字段可能会导致发生 **WillChangeRecord** 或 **RecordChangeComplete** 事件： [Update](update-method-ado.md)、[Delete](delete-method-ado-recordset.md)、[CancelUpdate](cancelupdate-method-ado.md)、[AddNew](addnew-method-ado.md)、[UpdateBatch](updatebatch-method-ado.md) 和 [CancelBatch](cancelbatch-method-ado.md)。 **Recordset** [CursorType](cursortype-property-ado.md)的值确定哪个操作导致事件发生。

**WillChangeRecord**事件期间， **Recordset** [Filter](filter-property-ado.md)属性设置为**adFilterAffectedRecords**。 在处理事件的时候不能更改此属性。

对于每个可能的 adReason 值，必须将 adStatus 参数设置为 adStatusUnwantedEvent，以完全停止包含 adReason 参数的任何事件的事件通知。

