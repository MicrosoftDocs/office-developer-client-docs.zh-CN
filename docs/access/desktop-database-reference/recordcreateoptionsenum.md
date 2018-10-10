---
title: RecordCreateOptionsEnum
TOCTitle: RecordCreateOptionsEnum
ms:assetid: 153dc8ff-680c-1482-d386-4c4b33ffc589
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248917(v=office.15)
ms:contentKeyID: 48543405
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b3315fc0b6d72689e36530b7e7daf7b94732459f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467327"
---
# <a name="recordcreateoptionsenum"></a>RecordCreateOptionsEnum


**适用于**： Access 2013 |Office 2013

指定应该打开现有的 **Record** 还是应该为 **Record** 对象 [Open](record-object-ado.md) 方法创建一个新 [Record](open-method-ado-record.md) 。可以使用 AND 运算符来组合使用这些值。

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
<td><p><strong>adCreateCollection</strong></p></td>
<td><p>0x2000</p></td>
<td><p>在由 <em>Source</em> 参数指定的节点创建一个新 <strong>Record</strong>，而不是打开现有的 <strong>Record</strong>。如果源指向现有节点，则发生运行时错误，除非将 <strong>adCreateCollection</strong> 与 <strong>adOpenIfExists</strong> 或 <strong>adCreateOverwrite</strong> 结合使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCreateNonCollection</strong></p></td>
<td><p>0</p></td>
<td><p>创建一个类型为 <a href="recordtypeenum.md">adSimpleRecord</a> 的新 <strong>Record</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adCreateOverwrite</strong></p></td>
<td><p>0x4000000</p></td>
<td><p>修改创建标志 <strong>adCreateCollection</strong>、<strong>adCreateNonCollection</strong> 和 <strong>adCreateStructDoc</strong>。当通过 OR 使用该值以及某个创建标志值时，如果源 URL 指向现有的节点或 <strong>Record</strong>，将覆盖该现有 <strong>Record</strong>，并在其位置创建一个新记录。该值不能与 <strong>adOpenIfExists</strong> 一起使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCreateStructDoc</strong></p></td>
<td><p>0x80000000</p></td>
<td><p>创建一个类型为 <a href="recordtypeenum.md">adStructDoc</a> 的新 <strong>Record</strong>，而不是打开现有 <strong>Record</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFailIfNotExists</strong></p></td>
<td><p>-1</p></td>
<td><p>默认值。如果 <em>Source</em> 指向不存在的节点，将发生运行时错误。</p></td>
</tr>
<tr class="even">
<td><p><strong>adOpenIfExists</strong></p></td>
<td><p>0x2000000</p></td>
<td><p>修改创建标志 <strong>adCreateCollection</strong>、<strong>adCreateNonCollection</strong> 和 <strong>adCreateStructDoc</strong>。当通过 OR 使用此值以及某个创建标志值时，如果源 URL 指向现有的节点或 <strong>Record</strong> 对象，则提供程序必须打开现有 <strong>Record</strong>，而不是创建新记录。此值不能与 <strong>adCreateOverwrite</strong> 一起使用。</p></td>
</tr>
</tbody>
</table>


**ADO/WFC 等效值**

这些常量没有 ADO/WFC 等效值。

