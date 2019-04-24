---
title: 与字段相关的错误信息
TOCTitle: Field-related error information
ms:assetid: 81a2c5a4-ab09-53d8-b270-e889b00a0c1a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249559(v=office.15)
ms:contentKeyID: 48545958
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3a0d0362b8f0ff9570a92a3c1c364061d1f9a584
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292970"
---
# <a name="field-related-error-information"></a>与字段相关的错误信息


**适用于**：Access 2013、Office 2013

如果错误与字段直接相关（例如，如果缺少数据或者对于该字段它是错误的类型），则可以通过检查 **Field** 对象的 **Status** 属性来检索有关问题原因的详细信息。此属性已得到增强，以提供有关问题的具体信息。因此，例如，在调用 **UpdateBatch** 失败时，可以通过检查每个受影响记录的 **Fields** 的 **Status** 属性来确定问题的原因。该属性将包含 **FieldStatusEnum** 常量中的一个值。下表包括在发生错误时需要特别注意的那些值。

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
<td><p><strong>adFieldCantConvertValue</strong></p></td>
<td><p>双面</p></td>
<td><p>指示由于丢失数据而无法检索或存储字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldDataOverflow</strong></p></td>
<td><p>型</p></td>
<td><p>指示从提供程序返回的数据使字段的数据类型发生溢出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldDefault</strong></p></td>
<td><p>13</p></td>
<td><p>指示在设置数据时使用字段的默认值。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldIgnore</strong></p></td>
<td><p>个</p></td>
<td><p>指示在设置数据源中的数据值时已跳过此字段。提供程序未设置值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldIntegrityViolation</strong></p></td>
<td><p>10</p></td>
<td><p>指示无法修改字段，因为它是计算得出的实体或派生实体。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFieldIsNull</strong></p></td>
<td><p>第三章</p></td>
<td><p>指示提供程序返回了 Null 值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFieldOutOfSpace</strong></p></td>
<td><p>22</p></td>
<td><p>指示提供程序无法获取足够的存储空间来完成移动或复制操作。</p></td>
</tr>
</tbody>
</table>

