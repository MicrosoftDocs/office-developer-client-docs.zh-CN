---
title: WillExecute 事件 (ADO)
TOCTitle: WillExecute event (ADO)
ms:assetid: 9f516bfd-246d-9817-4ca3-64598ab466f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249732(v=office.15)
ms:contentKeyID: 48546686
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2ea43f565199f346287abf8fd134dec494d37cf5
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949969"
---
# <a name="willexecute-event-ado"></a>WillExecute 事件 (ADO)

**适用于**： Access 2013、 Office 2013

**WillExecute** 事件在对连接执行挂起的命令之前的那一刻调用。

## <a name="syntax"></a>语法

WillExecute*源*， *CursorType*， *LockType*、*选项*、 *adStatus*、 *pCommand*、 *pRecordset*、 *pConnection*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*Source* |包含 SQL 命令或存储过程名称的 **字符串型** 。|
|*CursorType* |包含将打开的 [Recordset](cursortypeenum.md) 的游标类型的 **CursorTypeEnum**。 使用此参数，您可以将光标更改为任何类型， **Recordset** [打开](open-method-ado-recordset.md)操作过程中。 *CursorType*将被忽略任何其他操作。|
|*LockType* |包含将打开的 [Recordset](locktypeenum.md) 的锁类型的 **LockTypeEnum**。 使用此参数可以在 **Recordset** 的 **Open** 操作期间将锁更改为其他类型。 *LockType*将被忽略任何其他操作。|
|*Options* |**长整型** 值，指示可用于执行命令或打开 **Recordset** 的选项。|
|*adStatus* |[EventStatusEnum](eventstatusenum.md)。 此事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知，将该参数设置为 **adStatusCancel** 可以请求取消导致该事件的操作。|
|*pCommand* |为其应用该事件通知的 [Command](command-object-ado.md) 对象。|
|*pRecordset* |为其应用该事件通知的 [Recordset](recordset-object-ado.md) 对象。|
|*pConnection* |为其应用该事件通知的 [Connection](connection-object-ado.md) 对象。|

## <a name="remarks"></a>备注

**WillExecute**事件可能出现 0:**连接。**[执行](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection)**命令。**[执行](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command)，或**Recordset。**[Open](open-method-ado-recordset.md)方法的*pConnection*参数应始终包含对**Connection**对象的有效引用。 如果由于**Connection.Execute**事件，在*pRecordset*和*pCommand*参数设置为**Nothing**。 如果由于**Recordset.Open**事件， *pRecordset*参数将引用的**Recordset**对象和*pCommand*参数设置为**Nothing**。 如果由于**Command.Execute**事件， *pCommand*参数将引用的**Command**对象和*pRecordset*参数设置为**Nothing**。

**WillExecute** 允许您检查和修改挂起的执行的参数。该事件可以返回取消挂起的命令的请求。

