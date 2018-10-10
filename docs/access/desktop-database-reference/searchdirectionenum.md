---
title: SearchDirectionEnum
TOCTitle: SearchDirectionEnum
ms:assetid: d491000b-47d0-bb28-95ed-7526dbb7c5e9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250064(v=office.15)
ms:contentKeyID: 48547943
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d0a9954319448a219d9683cfd8133929fb3d184d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465986"
---
# <a name="searchdirectionenum"></a>SearchDirectionEnum


**适用于**： Access 2013 |Office 2013

用于指定 [Recordset](recordset-object-ado.md) 中记录搜索的方向。

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
<td><p><strong>adSearchBackward</strong></p></td>
<td><p>-1</p></td>
<td><p>向后搜索，在 <strong>Recordset</strong> 的开头停止。如果未找到匹配项，则记录指针定位在 <a href="bof-eof-properties-ado.md">BOF</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>adSearchForward</strong></p></td>
<td><p>1</p></td>
<td><p>向前搜索，在 <strong>Recordset</strong> 的末尾停止。如果未找到匹配项，则记录指针定位在 <a href="bof-eof-properties-ado.md">EOF</a>。</p></td>
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
<td><p>AdoEnums.SearchDirection.BACKWARD</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.SearchDirection.FORWARD</p></td>
</tr>
</tbody>
</table>

