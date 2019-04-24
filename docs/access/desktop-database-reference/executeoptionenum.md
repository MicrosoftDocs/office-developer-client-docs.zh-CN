---
title: ExecuteOptionEnum (Access desktop database reference)
TOCTitle: ExecuteOptionEnum
ms:assetid: bd6d44a3-e471-7aa0-3e65-6775334de2ff
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249915(v=office.15)
ms:contentKeyID: 48547438
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: febeb3b52eb579647c995b01d6723a5c1f1b0c1f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293243"
---
# <a name="executeoptionenum"></a>ExecuteOptionEnum

**适用于**：Access 2013、Office 2013

指定提供程序应当如何执行命令。

<br/>

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
<td><p>指示命令应异步执行。 此值不能与 <a href="commandtypeenum.md">CommandTypeEnum</a> 值 <strong>adCmdTableDirect</strong> 结合使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>adAsyncFetch</strong></p></td>
<td><p>0x20</p></td>
<td><p>指示应异步检索在 <a href="cachesize-property-ado.md">CacheSize</a> 属性中指定的初始数量之后剩余的行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>起作用</strong></p></td>
<td><p>0x40</p></td>
<td><p>指示主线程在检索期间永不阻塞。 如果未检索到请求的行，当前行将自动移动到文件的末尾。</p><p>如果从包含永久存储的 <strong>Recordset</strong> 的 <a href="stream-object-ado.md">Stream</a> 中打开 <a href="recordset-object-ado.md">Recordset</a>，<strong>adAsyncFetchNonBlocking</strong> 将无效；操作将同步且阻塞。 当使用 <a href="commandtypeenum.md">adCmdTableDirect</a> 选项来打开 <strong>Recordset</strong> 时，<strong>adAsynchFetchNonBlocking</strong> 无效。</p></td>
</tr>
<tr class="even">
<td><p><strong>adExecuteNoRecords</strong></p></td>
<td><p>0x80</p></td>
<td><p>指示命令文本是不返回行的命令或存储过程（如，仅插入数据的命令）。 如果检索到任何行，将丢弃它们而不是返回它们。 <strong>adExecuteNoRecords</strong>只能作为可选参数传递给<strong>Command</strong>或<strong>Connection</strong> <strong>Execute</strong>方法。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adExecuteStream</strong></p></td>
<td><p>0x400</p></td>
<td><p>指示命令执行的结果应作为流返回。 <strong>adExecuteStream</strong>只能作为可选参数传递给<strong>Command</strong> <strong>Execute</strong>方法。</p></td>
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


### <a name="adowfc-equivalent"></a>ADO/WFC 等效项

包：**com.ms.wfc.data**

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
<td><p>AdoEnums ExecuteOption</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums ExecuteOption</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums ExecuteOption</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums ExecuteOption</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums 不指定 ExecuteOption</p></td>
</tr>
</tbody>
</table>

