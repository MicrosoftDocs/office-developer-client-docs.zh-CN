---
title: WillMove 和 MoveComplete 事件 (ADO)
TOCTitle: WillMove and MoveComplete events (ADO)
ms:assetid: fe7eb823-b388-6b3d-1ae9-056018032ef5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250307(v=office.15)
ms:contentKeyID: 48548937
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e663e18a13803097d490e0e315d139e6e15400da
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306052"
---
# <a name="willmove-and-movecomplete-events-ado"></a>WillMove 和 MoveComplete 事件 (ADO)

**适用于**：Access 2013、Office 2013

在挂起操作更改 [Recordset](recordset-object-ado.md) 中的当前位置之前调用 **WillMove** 事件。在 **Recordset** 中的当前位置更改之后调用 **MoveComplete** 事件。

## <a name="syntax"></a>语法

WillMove*adReason*、 *adStatus*、 *pRecordset*

MoveComplete*adReason*、 *pError*、 *adStatus*、 *pRecordset*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*adReason* |指定此事件原因的 [EventReasonEnum](eventreasonenum.md) 值。其值可以是 **adRsnMoveFirst** 、 **adRsnMoveLast** 、 **adRsnMoveNext** 、 **adRsnMovePrevious** 、 **adRsnMove** 或 **adRsnRequery** 。|
|*pError* |[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。|
|*adStatus* |[EventStatusEnum](eventstatusenum.md)。 当调用**WillMove**时, 如果导致事件的操作成功, 则将此参数设置为**adstatusok;** 。 如果此事件无法请求取消挂起的操作, 则将其设置为**adStatusCantDeny** 。 <br/><br/>在调用 **MoveComplete** 时，如果引发事件的操作成功，则此参数设置为 **adStatusOK** ；如果操作失败则设置为 **adStatusErrorsOccurred** 。 <br/><br/>在 **WillMove** 返回之前，此参数设置为 **adStatusCancel** 以请求取消挂起操作，或设置为 adStatusUnwantedEvent 以禁止后续的通知。 <br/><br/>在 **MoveComplete** 返回之前，此参数设置为 **adStatusUnwantedEvent** 以禁止后续的通知。|
|*pRecordset* |[Recordset](recordset-object-ado.md) 对象。发生此事件的 **Recordset** 。|

## <a name="remarks"></a>注解

**WillMove**或**MoveComplete**事件可能是由以下**Recordset**操作导致的:

- [Open](open-method-ado-recordset.md)
- [Move](move-method-ado.md)
- [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)
- [MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)
- [MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 
- [MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)
- [AddNew](addnew-method-ado.md)
- [Requery](requery-method-ado.md)

这些事件可能因以下属性而发生:

- [Filter](filter-property-ado.md)
- [索引](index-property-ado.md)
- [Bookmark](bookmark-property-ado.md)
- [AbsolutePage](absolutepage-property-ado.md)
- [AbsolutePosition](absoluteposition-property-ado.md)

如果子 **Recordset** 与 **Recordset** 事件相连且父 **Recordset** 被移动，那么也有可能发生这两个事件。

对于每个可能的 *adReason* 值，必须将 **adStatus** 参数设置为 *adStatusUnwantedEvent*，才能完全阻止包括 *adReason* 参数的任何事件的事件通知。

