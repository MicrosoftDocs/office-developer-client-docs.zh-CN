---
title: ConnectModeEnum （访问桌面数据库参考 （英文）
TOCTitle: ConnectModeEnum
ms:assetid: a15aa733-f899-5fe9-e705-67a4301706d1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249743(v=office.15)
ms:contentKeyID: 48546728
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 6a09ea4d781e5560e335c2e75fc2da9a5508bae8
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25874004"
---
# <a name="connectmodeenum"></a>ConnectModeEnum

**适用于**： Access 2013、 Office 2013

指定可用于执行以下操作的权限：修改 [Connection](connection-object-ado.md) 中的数据、打开 [Record](record-object-ado.md)，或指定 [Record](mode-property-ado.md) 和 **Stream** 对象的 [Mode](stream-object-ado.md) 属性的值。

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
<td><p>3</p></td>
<td><p>指示读/写权限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adModeRecursive</strong></p></td>
<td><p>0x400000</p></td>
<td><p>与其他<em>*ShareDeny*</em>值 （<strong>adModeShareDenyNone</strong>、 <strong>adModeShareDenyWrite</strong>或<strong>adModeShareDenyRead</strong>） 传播到所有子记录当前<strong>记录</strong>的共享限制结合使用。 如果<strong>记录</strong>不具有任何子级，它会产生任何影响。</p><p>如果与<strong>adModeShareDenyNone</strong>仅使用，则生成运行时错误。 但是，它可以与<strong>adModeShareDenyNone</strong>与其他值结合时使用。 例如，您可以使用&quot; <strong>adModeRead</strong>或<strong>adModeShareDenyNone</strong>或<strong>adModeRecursive</strong>&quot;。</p></td>
</tr>
<tr class="even">
<td><p><strong>adModeShareDenyNone</strong></p></td>
<td><p>16</p></td>
<td><p>允许他人以任何权限打开连接。不能拒绝他人的读访问或写访问。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adModeShareDenyRead</strong></p></td>
<td><p>4</p></td>
<td><p>禁止他人以读权限打开连接。</p></td>
</tr>
<tr class="even">
<td><p><strong>adModeShareDenyWrite</strong></p></td>
<td><p>8</p></td>
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
<td><p>2</p></td>
<td><p>指示只写权限。</p></td>
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
<td><p>AdoEnums.ConnectMode.READ</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ConnectMode.READWRITE</p></td>
</tr>
<tr class="odd">
<td><p>（没有 AdoEnums.ConnectMode.RECURSIVE 的等效值）</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ConnectMode.SHAREDENYNONE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ConnectMode.SHAREDENYREAD</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ConnectMode.SHAREDENYWRITE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ConnectMode.SHAREEXCLUSIVE</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.ConnectMode.UNKNOWN</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.ConnectMode.WRITE</p></td>
</tr>
</tbody>
</table>

