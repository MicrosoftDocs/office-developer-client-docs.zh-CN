---
title: MoveRecordOptionsEnum
TOCTitle: MoveRecordOptionsEnum
ms:assetid: 2785bca0-777c-a802-51d7-6f5cf0fb4210
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249039(v=office.15)
ms:contentKeyID: 48543842
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fc621f620a7d55571aa55296a4d294fff9566bf5
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862238"
---
# <a name="moverecordoptionsenum"></a>MoveRecordOptionsEnum


**适用于**： Access 2013 |Office 2013

指定 [Record](record-object-ado.md) 对象的 [MoveRecord](moverecord-method-ado.md) 方法的行为。

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
<td><p><strong>adMoveUnspecified</strong></p></td>
<td><p>-1</p></td>
<td><p>默认值。执行默认移动操作：如果目标文件或目录已存在，则操作失败，并且更新超文本链接。</p></td>
</tr>
<tr class="even">
<td><p><strong>adMoveOverWrite</strong></p></td>
<td><p>1</p></td>
<td><p>覆盖目标文件或目录，即使它已存在。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adMoveDontUpdateLinks</strong></p></td>
<td><p>2</p></td>
<td><p>通过不更新源 <strong>Record</strong> 的超文本链接来修改 <strong>MoveRecord</strong> 方法的默认行为。默认行为取决于提供程序的功能。如果提供程序具有相应功能，则移动操作更新链接。如果提供程序无法修复链接或者如果未指定该值，则即使链接尚未修复，移动也会成功。</p></td>
</tr>
<tr class="even">
<td><p><strong>adMoveAllowEmulation</strong></p></td>
<td><p>4</p></td>
<td><p>提供程序尝试模拟移动（使用下载、上载和删除操作）的请求。如果移动 <strong>Record</strong> 的尝试由于目标 URL 在不同的服务器或者由非源提供程序提供服务而失败，可能会导致增加延迟或数据丢失，原因是在提供程序之间移动资源时，各个提供程序具有不同的功能。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效值

这些常量没有 ADO/WFC 等效值。

