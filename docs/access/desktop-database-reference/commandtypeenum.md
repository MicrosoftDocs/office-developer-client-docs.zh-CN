---
title: CommandTypeEnum (Access desktop database reference)
TOCTitle: CommandTypeEnum
ms:assetid: 9ad8f155-88a0-00eb-2855-1e1a2a677437
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249700(v=office.15)
ms:contentKeyID: 48546549
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a9114128771d4753265208dada763ac0c9f796d1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296113"
---
# <a name="commandtypeenum"></a>CommandTypeEnum

**适用于**：Access 2013、Office 2013

指定应当如何解释命令参数。

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
<td><p><strong>adCmdUnspecified</strong></p></td>
<td><p>-1</p></td>
<td><p>不指定命令类型参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCmdText</strong></p></td>
<td><p>1</p></td>
<td><p>将 <a href="commandtext-property-ado.md">CommandText</a> 求值为命令或存储过程调用的文字定义。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adCmdTable</strong></p></td>
<td><p>双面</p></td>
<td><p>将 <strong>CommandText</strong> 求值为表名，该表中的列全部由内部生成的 SQL 查询返回。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCmdStoredProc</strong></p></td>
<td><p>4</p></td>
<td><p>将 <strong>CommandText</strong> 求值为存储过程名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adCmdUnknown</strong></p></td>
<td><p>utf-8</p></td>
<td><p>默认值。指示 <strong>CommandText</strong> 属性中的命令类型未知。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCmdFile</strong></p></td>
<td><p>256</p></td>
<td><p>将 <strong>CommandText</strong> 求值为永久存储的 <a href="recordset-object-ado.md">Recordset</a> 的文件名。仅与 <strong>Recordset.</strong><a href="open-method-ado-recordset.md">Open</a> 或 <a href="requery-method-ado.md">Requery</a> 一起使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adCmdTableDirect</strong></p></td>
<td><p>512</p></td>
<td><p>将 <strong>CommandText</strong> 求值为表名，该表中的列全部返回。 仅与 <strong>Recordset.Open</strong> 或 <strong>Requery</strong> 一起使用。 要使用 <a href="seek-method-ado.md">Seek</a> 方法，必须使用 <strong>adCmdTableDirect</strong> 打开 <strong>Recordset</strong>。 此值不能与 <a href="executeoptionenum.md">ExecuteOptionEnum</a> 值 <strong>adAsyncExecute</strong> 组合使用。</p></td>
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
<td><p>AdoEnums 不指定 CommandType</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums 的 CommandType</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums CommandType</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums CommandType</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums CommandType</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums CommandType</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums CommandType</p></td>
</tr>
</tbody>
</table>

