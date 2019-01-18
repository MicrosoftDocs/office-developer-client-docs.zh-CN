---
title: EndOfRecordset 事件 (ADO)
TOCTitle: EndOfRecordset event (ADO)
ms:assetid: 8995b851-dff6-2525-1d62-a2cfb4f95393
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249603(v=office.15)
ms:contentKeyID: 48546167
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 48e0eb25b443175013a144fafaa433df12c2cc9c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721358"
---
# <a name="endofrecordset-event-ado"></a>EndOfRecordset 事件 (ADO)

**适用于**： Access 2013、 Office 2013

当尝试移动到 **Recordset** 末尾之后的某一行时，调用 [EndOfRecordset](recordset-object-ado.md) 事件。

## <a name="syntax"></a>语法

EndOfRecordset*fMoreData*， *adStatus* *pRecordset*

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*fMoreData* |A **VARIANT\_BOOL**值，如果设置为 VARIANT\_值为 TRUE，指示已向**Recordset**添加更多行。|
|*adStatus* |[EventStatusEnum](eventstatusenum.md)。 当调用**EndOfRecordset**时，此参数设置为**adStatusOK**如果导致事件的操作成功。 如果此事件不能请求取消导致该事件的操作，它是设置为**adStatusCantDeny** 。<br/><br/>在 **EndOfRecordset** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。|
|*pRecordset* | **Recordset** 对象。发生此事件的 **Recordset** 。|

## <a name="remarks"></a>备注

如果 **MoveNext** 操作失败，可能会发生 [EndOfRecordset](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 事件。

当尝试移动到 **Recordset** 对象末尾之后的位置时（可能是作为调用 **MoveNext** 的结果），调用该事件处理程序。 但是，在该事件中，您可以从数据库中检索更多记录并将它们追加到 **Recordset** 的末尾。 在这种情况下，将*fMoreData*设置为 VARIANT\_为 TRUE，并从**EndOfRecordset**返回。 然后再次调用 **MoveNext** 以访问最新检索到的记录。

