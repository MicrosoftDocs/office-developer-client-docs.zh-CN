---
title: ExecuteComplete 事件 (ADO)
TOCTitle: ExecuteComplete Event (ADO)
ms:assetid: 47317d97-e373-32f4-9438-2dff46b8d367
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249219(v=office.15)
ms:contentKeyID: 48544589
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 231cfcf42cead3074996870971488dadb60583ae
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605417"
---
# <a name="executecomplete-event-ado"></a>ExecuteComplete 事件 (ADO)


**适用于**： Access 2013 |Office 2013



**ExecuteComplete** 事件在命令执行完毕之后调用。

## <a name="syntax"></a>语法

ExecuteComplete*RecordsAffected*， *pError*、 *adStatus*、 *pCommand*、 *pRecordset*、 *pConnection*

## <a name="parameters"></a>参数

  - *RecordsAffected*

  - **长整型** 值，指示受命令影响的记录数。

  - *pError*

  - [Error](error-object-ado.md) 对象。如果 **adStatus** 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。

  - *adStatus*

  - [EventStatusEnum](eventstatusenum.md)
    
    在此事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。

  - *pCommand*

  - 已执行的 [Command](command-object-ado.md) 对象。即使在不显式创建 **Command** 的情况下调用 **Connection.Execute** 或 **Recordset.Open** 时（在这种情况下， **Command** 对象由 ADO 在内部创建），也包含一个 **Command** 对象。

  - *pRecordset*

  - 作为已执行命令的结果的 [Recordset](recordset-object-ado.md) 对象。该 **Recordset** 可以为空。您绝不能从该事件处理程序内销毁此 Recordset 对象，否则，当 ADO 尝试访问不再存在的对象时，会导致违规存取错误。

  - *pConnection*

  - [Connection](connection-object-ado.md) 对象。操作通过该连接执行。

## <a name="remarks"></a>备注

<<<<<<< 标头**ExecuteComplete**事件可能出现 0:**连接。**[执行](https://msdn.microsoft.com/library/jj249832\(v=office.15\))**命令。**[执行](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) **Recordset。**[打开](open-method-ado-recordset.md)， **Recordset。**[Requery](requery-method-ado.md)或**Recordset。**[NextRecordset](nextrecordset-method-ado.md)方法。
=== **ExecuteComplete**事件可能出现 0:**连接。**[执行](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection)**命令。**[执行](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) **Recordset。**[打开](open-method-ado-recordset.md)， **Recordset。**[Requery](requery-method-ado.md)或**Recordset。**[NextRecordset](nextrecordset-method-ado.md)方法。
>>>>>>> master

