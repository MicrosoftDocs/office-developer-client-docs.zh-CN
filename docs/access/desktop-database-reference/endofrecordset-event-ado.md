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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293558"
---
# <a name="endofrecordset-event-ado"></a>EndOfRecordset 事件 (ADO)

**适用于**：Access 2013、Office 2013

当尝试移动到 [Recordset](recordset-object-ado.md) 末尾之后的某一行时，调用 **EndOfRecordset** 事件。

## <a name="syntax"></a>语法

EndOfRecordset*fMoreData*、 *adStatus*、 *pRecordset*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*fMoreData* |**\_variant BOOL**值, 如果设置为 VARIANT\_TRUE, 则表示已向**Recordset**添加了更多的行。|
|*adStatus* |[EventStatusEnum](eventstatusenum.md)。 当调用**EndOfRecordset**时, 如果导致事件的操作成功, 则将此参数设置为**adstatusok;** 。 如果此事件不能请求取消导致该事件的操作, 则将其设置为**adStatusCantDeny** 。<br/><br/>在 **EndOfRecordset** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。|
|*pRecordset* | **Recordset** 对象。发生此事件的 **Recordset** 。|

## <a name="remarks"></a>注解

如果 **MoveNext** 操作失败，可能会发生 [EndOfRecordset](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 事件。

当尝试移动到 **Recordset** 对象末尾之后的位置时（可能是作为调用 **MoveNext** 的结果），调用该事件处理程序。 但是，在该事件中，您可以从数据库中检索更多记录并将它们追加到 **Recordset** 的末尾。 在这种情况下** , 将 fMoreData\_设置为 VARIANT TRUE, 然后从**EndOfRecordset**返回。 然后再次调用 **MoveNext** 以访问最新检索到的记录。

