---
title: 确定编辑模式
TOCTitle: Determining Edit mode
ms:assetid: 45e21fa7-94e8-3449-e062-09cbcf15cba8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249215(v=office.15)
ms:contentKeyID: 48544563
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b5b62bc282a99472d0e7399ee9f3dd9d0648f0c7
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698748"
---
# <a name="determining-edit-mode"></a>确定编辑模式


**适用于**： Access 2013、 Office 2013

ADO 维护一个与当前记录关联的编辑缓冲区。 **EditMode** 属性指示此缓冲区是否已发生更改，或者是否已创建新记录。使用 **EditMode** 可以确定当前记录的编辑状态。如果编辑过程已经中断则可以测试是否有挂起更改，并确定是否需要使用 **Update** 或 **CancelUpdate** 方法。

**EditMode** 返回 **EditModeEnum** 常量之一，下表列出了这些常量。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>为 adEditNone</strong></p></td>
<td><p>指示没有正在进行的编辑操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>adEditInProgress</strong></p></td>
<td><p>指示当前记录中的数据已经修改但未保存。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adEditAdd</strong></p></td>
<td><p>指示已调用 <strong>AddNew</strong> 方法，并且复制缓冲区中的当前记录是尚未保存到数据库的新记录。</p></td>
</tr>
<tr class="even">
<td><p><strong>adEditDelete</strong></p></td>
<td><p>指示已删除当前记录。</p></td>
</tr>
</tbody>
</table>


只有当存在当前记录时， **EditMode** 才能返回有效值。如果 **BOF** 或 **EOF** 为 **True** 或当前记录已删除， **EditMode** 将返回错误。

