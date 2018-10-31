---
title: StringFormatEnum （访问桌面数据库参考 （英文）
TOCTitle: StringFormatEnum
ms:assetid: ab069d67-d983-f390-5d45-876a9f9d9691
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249794(v=office.15)
ms:contentKeyID: 48546964
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 8a3b798fd0d10a3bb2c1c4bd03419a6d506bbf8b
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25863036"
---
# <a name="stringformatenum"></a>StringFormatEnum

**适用于**： Access 2013 |Office 2013

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
<td><p>2</p></td>
<td><p>用 <em>RowDelimiter</em> 分隔行，用 <em>ColumnDelimiter</em> 分隔列，用 <em>NullExpr</em> 分隔空值。<a href="getstring-method-ado.md">GetString</a> 方法的这三个参数仅在与 <strong>adClipString</strong> 的 <em>StringFormat</em> 一起使用时有效。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效值

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
<td><p>AdoEnums.StringFormat.CLIPSTRING</p></td>
</tr>
</tbody>
</table>

