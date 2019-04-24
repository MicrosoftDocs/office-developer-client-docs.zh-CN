---
title: UpdateTypeEnum 枚举 (DAO)
TOCTitle: UpdateTypeEnum Enumeration
ms:assetid: 7ac38bae-27fc-f3d0-5b75-569bce547954
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196186(v=office.15)
ms:contentKeyID: 48545800
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d1e4ecbc216ab4a00dabd85f623bc134772dfd4c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306186"
---
# <a name="updatetypeenum-enumeration-dao"></a>UpdateTypeEnum 枚举 (DAO)


**适用于**：Access 2013、Office 2013

与 **Update** 方法一起用来指定要写入到磁盘中的更新。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dbUpdateBatch</p></td>
<td><p>4</p></td>
<td><p>将更新缓存中的所有挂起的更改写入磁盘中。</p></td>
</tr>
<tr class="even">
<td><p>dbUpdateCurrentRecord</p></td>
<td><p>双面</p></td>
<td><p>仅将当前记录的挂起更改写入磁盘中。</p></td>
</tr>
<tr class="odd">
<td><p>dbUpdateRegular</p></td>
<td><p>1</p></td>
<td><p>（默认值）挂起的更改不进行缓存，直接写入磁盘中。</p></td>
</tr>
</tbody>
</table>

