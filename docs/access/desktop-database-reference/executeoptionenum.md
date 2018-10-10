---
title: ExecuteOptionEnum （访问桌面数据库参考 （英文）
TOCTitle: ExecuteOptionEnum
ms:assetid: bd6d44a3-e471-7aa0-3e65-6775334de2ff
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249915(v=office.15)
ms:contentKeyID: 48547438
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: aeb1083c693e0848e30a0b9217ae709994daddb5
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467064"
---
# <a name="executeoptionenum"></a>ExecuteOptionEnum


**适用于**： Access 2013 |Office 2013

指定提供程序应当如何执行命令。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adAsyncExecute</strong></p></td>
<td><p>0x10</p></td>
<td><p>指示命令应异步执行。
 此值不能与 <a href="commandtypeenum.md">CommandTypeEnum</a> 值 <strong>adCmdTableDirect</strong> 结合使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>adAsyncFetch</strong></p></td>
<td><p>0x20</p></td>
<td><p>指示应异步检索在 <a href="cachesize-property-ado.md">CacheSize</a> 属性中指定的初始数量之后剩余的行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>持久性</strong></p></td>
<td><p>0x40</p></td>
<td><p>指示主线程永远不会阻止检索时。 如果检索不到请求的行，当前行将自动移动到文件末尾。 如果从包含永久存储的 <strong>Recordset</strong> 的 <a href="stream-object-ado.md">Stream</a> 中打开 <a href="recordset-object-ado.md">Recordset</a>，<strong>adAsyncFetchNonBlocking</strong> 将无效；操作将同步且阻塞。 当使用 <a href="commandtypeenum.md">adCmdTableDirect</a> 选项来打开 <strong>Recordset</strong> 时，<strong>adAsynchFetchNonBlocking</strong> 无效。</p></td>
</tr>
<tr class="even">
<td><p><strong>adExecuteNoRecords</strong></p></td>
<td><p>0x80</p></td>
<td><p>指示命令文本的命令或存储的过程的不返回行 （例如，仅在插入数据的命令）。 如果检索任何行时，它们是丢弃，并且不会返回。 <strong>adExecuteNoRecords</strong>到<strong>Command</strong>或<strong>Connection</strong> <strong>Execute</strong>方法只能作为可选参数传递。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adExecuteStream</strong></p></td>
<td><p>0x400</p></td>
<td><p>指示命令执行的结果应作为流返回。
 <strong>adExecuteStream</strong>到<strong>命令</strong> <strong>Execute</strong>方法只能作为可选参数传递。</p></td>
</tr>
<tr class="even">
<td><p><strong>adExecuteRecord</strong></p></td>
<td><p><br />
</p></td>
<td><p>指示 <strong>CommandText</strong> 是返回单个行（它应该作为 <strong>Record</strong> 对象返回）的命令或存储过程。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adOptionUnspecified</strong></p></td>
<td><p>-1</p></td>
<td><p>指示未指定命令。</p></td>
</tr>
</tbody>
</table>


**ADO/WFC 等效值**

包： **com.ms.wfc.data**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AdoEnums.ExecuteOption.ASYNCEXECUTE</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ExecuteOption.ASYNCFETCH</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ExecuteOption.ASYNCFETCHNONBLOCKING</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ExecuteOption.NORECORDS</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ExecuteOption.UNSPECIFIED</p></td>
</tr>
</tbody>
</table>

