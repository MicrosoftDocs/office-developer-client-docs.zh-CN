---
title: StringFormatEnum (Access desktop database reference)
TOCTitle: StringFormatEnum
ms:assetid: ab069d67-d983-f390-5d45-876a9f9d9691
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249794(v=office.15)
ms:contentKeyID: 48546964
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 89eb3e9c972b19bc9908f29ce5ec5e42c8974d54
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314460"
---
# <a name="stringformatenum"></a>StringFormatEnum

**适用于**：Access 2013、Office 2013

用于将检索 [Recordset](recordset-object-ado.md) 时使用的格式指定为字符串。

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
<td><p><strong>adClipString</strong></p></td>
<td><p>双面</p></td>
<td><p>用 <em>RowDelimiter</em> 分隔行，用 <em>ColumnDelimiter</em> 分隔列，用 <em>NullExpr</em> 分隔空值。<a href="getstring-method-ado.md">GetString</a> 方法的这三个参数仅在与 <strong>adClipString</strong> 的 <em>StringFormat</em> 一起使用时有效。</p></td>
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
<td><p>AdoEnums adclipstring</p></td>
</tr>
</tbody>
</table>

