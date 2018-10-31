---
title: CopyRecordOptionsEnum
TOCTitle: CopyRecordOptionsEnum
ms:assetid: ab9426e9-0e4e-6c85-43cf-e4a205a7c4c0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249795(v=office.15)
ms:contentKeyID: 48546975
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b33347492562d868781e8bbca346918d55ed597b
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860278"
---
# <a name="copyrecordoptionsenum"></a>CopyRecordOptionsEnum


**适用于**： Access 2013 |Office 2013

指定 [CopyRecord](copyrecord-method-ado.md) 方法的行为。

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
<td><p><strong>adCopyAllowEmulation</strong></p></td>
<td><p>4</p></td>
<td><p>指示如果此方法由于 <em>Destination</em> 在不同的服务器上而失败或者由不同于 <em>Source</em> 提供程序的提供程序提供服务，则 <em>Source</em> 提供程序会尝试使用下载和上载操作来模拟复制。注意，不同的提供程序功能可能会导致性能下降或数据丢失。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCopyNonRecursive</strong></p></td>
<td><p>2</p></td>
<td><p>将当前目录（但不包括其任何子目录）复制到目标。此复制操作不是递归的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adCopyOverWrite</strong></p></td>
<td><p>1</p></td>
<td><p>如果 <em>Destination</em> 指向现有的文件或目录，则覆盖它们。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCopyUnspecified</strong></p></td>
<td><p>-1</p></td>
<td><p>默认值。执行默认复制操作：如果目标文件或目录已存在，则操作失败，并递归复制。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效值

这些常量没有 ADO/WFC 等效值。

