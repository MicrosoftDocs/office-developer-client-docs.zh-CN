---
title: ADO 事件处理程序摘要
TOCTitle: ADO event handler summary
ms:assetid: f50b9eb4-df6e-7b9d-0b3d-dca8945167a2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250247(v=office.15)
ms:contentKeyID: 48548701
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d18414793d6a28450dea349e03624ad7aa2537f9
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25945360"
---
# <a name="ado-event-handler-summary"></a>ADO 事件处理程序摘要


**适用于**： Access 2013、 Office 2013

两个 ADO 对象可以引发事件：[Connection](connection-object-ado.md) 对象和 [Recordset](recordset-object-ado.md) 对象。 **ConnectionEvent** 系列用于针对 **Connection** 对象的操作，而 **RecordsetEvent** 系列用于针对 **Recordset** 对象的操作。

- **连接事件** ：在以下情况下发出事件：当连接上的事务启动、提交或回滚时；当 [Command](command-object-ado.md) 执行时；当 **连接事件** 操作期间发生警告时；或者当 **Connection** 开始或结束时。

- **记录集事件** ：在以下情况下发出事件：在进行异步获取操作时，在 **Recordset** 对象的行中导航时，更改 **Recordset** 行中的字段时，更改 **Recordset** 中的行时，用服务器端游标打开 **Recordset** 时，关闭 **Recordset** 时，或在 **Recordset** 中进行任何更改时。

下表汇总了事件及其说明。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>ConnectionEvent</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">BeginTransComplete</a>、 CommitTransComplete RollbackTransComplete</p></td>
<td><p><strong>事务管理</strong>
					 - 通知连接上的当前事务已经启动、提交或回滚。</p></td>
</tr>
<tr class="even">
<td><p><a href="willconnect-event-ado.md">WillConnect</a>， <a href="connectcomplete-and-disconnect-events-ado.md">ConnectComplete，断开连接</a></p></td>
<td><p><strong>连接管理</strong>
					 - 通知当前连接将开始、已经开始或已经结束。</p></td>
</tr>
<tr class="odd">
<td><p><a href="willexecute-event-ado.md">WillExecute</a> <a href="executecomplete-event-ado.md">ExecuteComplete</a></p></td>
<td><p><strong>命令执行管理</strong>
					 - 通知将开始对连接执行当前命令，或已经结束。</p></td>
</tr>
<tr class="even">
<td><p><a href="infomessage-event-ado.md">InfoMessage</a></p></td>
<td><p><strong>信息</strong>
					 - 通知存在有关当前操作的其他信息。</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>RecordsetEvent</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="fetchprogress-event-ado.md">FetchProgress</a> <a href="fetchcomplete-event-ado.md">FetchComplete</a></p></td>
<td><p><strong>检索状态</strong>
					 - 通知数据检索操作的进度或检索操作已经完成。只有当 <strong>Recordset</strong> 是使用客户端游标打开时，这些事件才可用。</p></td>
</tr>
<tr class="even">
<td><p><a href="willchangefield-and-fieldchangecomplete-events-ado.md">WillChangeField FieldChangeComplete</a></p></td>
<td><p><strong>字段更改管理</strong>
					 - 通知当前字段的值将更改或已经更改。</p></td>
</tr>
<tr class="odd">
<td><p><a href="willmove-and-movecomplete-events-ado.md">WillMove、 MoveComplete</a> <a href="endofrecordset-event-ado.md">EndOfRecordset</a></p></td>
<td><p><strong>导航管理</strong>
					 - 通知 <strong>Recordset</strong> 中的当前行位置将更改、已经更改或已经到达 <strong>Recordset</strong> 的末尾。</p></td>
</tr>
<tr class="even">
<td><p><a href="willchangerecord-and-recordchangecomplete-events-ado.md">WillChangeRecord RecordChangeComplete</a></p></td>
<td><p><strong>行更改管理</strong>
					 - 通知 <strong>Recordset</strong> 的当前行中的某些内容将更改或已经更改。</p></td>
</tr>
<tr class="odd">
<td><p><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">在 WillChangeRecordset RecordsetChangeComplete</a></p></td>
<td><p><strong>记录集更改管理</strong>
					 - 通知当前 <strong>Recordset</strong> 中的某些内容将更改或已经更改。</p></td>
</tr>
</tbody>
</table>

