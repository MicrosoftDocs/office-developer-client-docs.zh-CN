---
title: PersistFormatEnum （访问桌面数据库参考 （英文）
TOCTitle: PersistFormatEnum
ms:assetid: 5aa99a63-d422-0812-5aba-19305a3ad405
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249313(v=office.15)
ms:contentKeyID: 48545050
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: a1e980debebe6a38ed0c27eabba3abefcd8be152
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887150"
---
# <a name="persistformatenum"></a>PersistFormatEnum

**适用于**： Access 2013、 Office 2013

指定保存 [Recordset](recordset-object-ado.md) 时所用的格式。

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
<td><p><strong>adPersistADTG</strong></p></td>
<td><p>0</p></td>
<td><p>指示 Microsoft 高级数据表图 (ADTG) 格式。</p></td>
</tr>
<tr class="even">
<td><p><strong>adPersistADO</strong></p></td>
<td><p>1</p></td>
<td><p>指示将使用 ADO 自己的可扩展标记语言 (XML) 格式。此值与 adPersistXML 相同，包括它的目的是为了向后兼容。</p></td>
</tr>
<tr class="odd">
<td><p><strong>xml 格式持久化记录</strong></p></td>
<td><p>1</p></td>
<td><p>指示可扩展标记语言 (XML) 格式。</p></td>
</tr>
<tr class="even">
<td><p><strong>adPersistProviderSpecific</strong></p></td>
<td><p>2</p></td>
<td><p>指示提供程序将使用自己的格式来持久化 <strong>Recordset</strong>。</p></td>
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
<td><p>AdoEnums.PersistFormat.ADTG</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.PersistFormat.XML</p></td>
</tr>
</tbody>
</table>

