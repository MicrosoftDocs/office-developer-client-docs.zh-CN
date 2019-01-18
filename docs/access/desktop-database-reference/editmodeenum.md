---
title: EditModeEnum （访问桌面数据库参考 （英文）
TOCTitle: EditModeEnum
ms:assetid: 4da0e504-aca2-b769-04a2-0df687fa4422
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249248(v=office.15)
ms:contentKeyID: 48544737
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 246d9e29f084efb975783fd15c15993eba5a6e74
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726286"
---
# <a name="editmodeenum"></a>EditModeEnum

**适用于**： Access 2013、 Office 2013

指定记录的编辑状态。

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
<td><p><strong>为 adEditNone</strong></p></td>
<td><p>0</p></td>
<td><p>指示没有正在进行的编辑操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>adEditInProgress</strong></p></td>
<td><p>1</p></td>
<td><p>指示当前记录中的数据已经修改但未保存。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adEditAdd</strong></p></td>
<td><p>2</p></td>
<td><p>指示已调用 <a href="addnew-method-ado.md">AddNew</a> 方法，且复制缓冲区中的当前记录是尚未保存在数据库中保存的新记录。</p></td>
</tr>
<tr class="even">
<td><p><strong>adEditDelete</strong></p></td>
<td><p>4</p></td>
<td><p>指示已删除当前记录。</p></td>
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
<td><p>AdoEnums.EditMode.NONE</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.EditMode.INPROGRESS</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.EditMode.ADD</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.EditMode.DELETE</p></td>
</tr>
</tbody>
</table>

