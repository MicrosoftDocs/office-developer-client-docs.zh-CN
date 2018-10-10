---
title: CursorLocationEnum （访问桌面数据库参考 （英文）
TOCTitle: CursorLocationEnum
ms:assetid: 520cc738-998b-ce80-6362-0df310c40c39
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249268(v=office.15)
ms:contentKeyID: 48544836
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 90226413579a8fac7586cbd5ef08510a36a42959
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466890"
---
# <a name="cursorlocationenum"></a>CursorLocationEnum


**适用于**： Access 2013 |Office 2013

用于指定游标服务的位置。

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
<td><p>3</p></td>
<td><p>使用由本地游标库提供的客户端游标。 本地游标服务通常将允许驱动程序提供的游标可能不会的许多功能，以便使用此设置可能会提供一个优点相对于将启用的功能。 向后兼容性，还支持同义词<strong>adUseClientBatch</strong> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>adUseNone</strong></p></td>
<td><p>1</p></td>
<td><p>不使用游标服务。（此常量已过时，仅仅为了向后兼容而出现。）</p></td>
</tr>
<tr class="odd">
<td><p><strong>为 adUseServer</strong></p></td>
<td><p>2</p></td>
<td><p>默认值。使用数据提供程序或驱动程序提供的游标。这些游标有时候非常灵活，允许对他人对数据源所做的更改具有额外的敏感度。但是，<a href="microsoft-cursor-service-for-ole-db-ado-service-component.md">Microsoft Cursor Service for OLE DB</a> 的某些功能（例如未关联的 <a href="recordset-object-ado.md">Recordset</a> 对象）无法使用服务器端游标进行模拟，因此，使用此设置时这些功能将不可用。</p></td>
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
<td><p>AdoEnums.CursorLocation.CLIENT</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.CursorLocation.NONE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.CursorLocation.SERVER</p></td>
</tr>
</tbody>
</table>

