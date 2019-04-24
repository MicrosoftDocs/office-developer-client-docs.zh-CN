---
title: 为 cursorlocationenum (Access desktop database reference)
TOCTitle: CursorLocationEnum
ms:assetid: 520cc738-998b-ce80-6362-0df310c40c39
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249268(v=office.15)
ms:contentKeyID: 48544836
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 95e5744d5e19e7c3d40de19e240bbe338b2d5d55
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295210"
---
# <a name="cursorlocationenum"></a>CursorLocationEnum

**适用于**：Access 2013、Office 2013

用于指定游标服务的位置。

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
<td><p><strong>adUseClient</strong></p></td>
<td><p>第三章</p></td>
<td><p>使用由本地游标库提供的客户端游标。 本地游标服务通常能够允许驱动程序提供的游标所不允许的许多功能，因此，对于将要启用的功能来说，使用此设置可以提供便利。 为了向后兼容，还支持同义词 <strong>adUseClientBatch</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>adUseNone</strong></p></td>
<td><p>1</p></td>
<td><p>不使用游标服务。（此常量已过时，仅仅为了向后兼容而出现。）</p></td>
</tr>
<tr class="odd">
<td><p><strong>adUseServer</strong></p></td>
<td><p>双面</p></td>
<td><p>默认值。 使用数据提供程序或驱动程序提供的游标。 这些游标有时候非常灵活，允许对他人对数据源所做的更改具有额外的敏感度。 但是, <a href="microsoft-cursor-service-for-ole-db-ado-service-component.md">Microsoft Cursor Service for OLE DB</a> (如未关联的<a href="recordset-object-ado.md">Recordset</a>对象) 的某些功能无法使用服务器端游标进行模拟, 并且这些功能将在此设置中不可用。</p></td>
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
<td><p>AdoEnums CursorLocation</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums CursorLocation</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums CursorLocation</p></td>
</tr>
</tbody>
</table>

