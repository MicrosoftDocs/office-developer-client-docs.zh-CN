---
title: ConnectModeEnum (Access desktop database reference)
TOCTitle: ConnectModeEnum
ms:assetid: a15aa733-f899-5fe9-e705-67a4301706d1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249743(v=office.15)
ms:contentKeyID: 48546728
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 453d84e687a31f7df5082e17b80fe2a1bda756be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295693"
---
# <a name="connectmodeenum"></a>ConnectModeEnum

**适用于**：Access 2013、Office 2013

指定可用于执行以下操作的权限：修改 [Connection](connection-object-ado.md) 中的数据、打开 [Record](record-object-ado.md)，或指定 **Record** 和 [Stream](stream-object-ado.md) 对象的 [Mode](mode-property-ado.md) 属性的值。

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
<td><p><strong>adModeRead</strong></p></td>
<td><p>1</p></td>
<td><p>指示只读属性。</p></td>
</tr>
<tr class="even">
<td><p><strong>adModeReadWrite</strong></p></td>
<td><p>第三章</p></td>
<td><p>指示读/写权限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adModeRecursive</strong></p></td>
<td><p>0x400000</p></td>
<td><p>与其他<em>*ShareDeny*</em>值 (<strong>adModeShareDenyNone</strong>、 <strong>adModeShareDenyWrite</strong>或<strong>adModeShareDenyRead</strong>) 结合使用, 以将共享限制传播到当前<strong>记录</strong>的所有子记录。 如果 <strong>Record</strong> 没有任何子记录，则该值无效。</p><p>如果将它仅与 <strong>adModeShareDenyNone</strong> 一起使用，将生成运行时错误。 但是，当与其他值组合使用时，可以将它与 <strong>adModeShareDenyNone</strong> 一起使用。 例如, 可以使用&quot; <strong>adModeRead</strong>或<strong>adModeShareDenyNone</strong>或<strong>adModeRecursive</strong>&quot;。</p></td>
</tr>
<tr class="even">
<td><p><strong>adModeShareDenyNone</strong></p></td>
<td><p>位</p></td>
<td><p>允许他人以任何权限打开连接。不能拒绝他人的读访问或写访问。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adModeShareDenyRead</strong></p></td>
<td><p>4</p></td>
<td><p>禁止他人以读权限打开连接。</p></td>
</tr>
<tr class="even">
<td><p><strong>adModeShareDenyWrite</strong></p></td>
<td><p>utf-8</p></td>
<td><p>禁止他人以写权限打开连接。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adModeShareExclusive</strong></p></td>
<td><p>12</p></td>
<td><p>禁止其他人打开连接。</p></td>
</tr>
<tr class="even">
<td><p><strong>adModeUnknown</strong></p></td>
<td><p>0</p></td>
<td><p>默认值。指示尚未设置权限或者无法确定权限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adModeWrite</strong></p></td>
<td><p>双面</p></td>
<td><p>指示只写权限。</p></td>
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
<td><p>AdoEnums。请参阅 ConnectMode</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums ConnectMode</p></td>
</tr>
<tr class="odd">
<td><p>（没有 AdoEnums.ConnectMode.RECURSIVE 的等效值）</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums ConnectMode</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums ConnectMode</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums ConnectMode</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums ConnectMode</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums ConnectMode</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums ConnectMode</p></td>
</tr>
</tbody>
</table>

