---
title: RightsEnum （访问桌面数据库参考 （英文）
TOCTitle: RightsEnum
ms:assetid: 7647b9d5-5271-fdcf-489d-5a8beb931ca5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249485(v=office.15)
ms:contentKeyID: 48545693
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3c7bf2f88632265cda7537215f2ea3c68507f16f
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706602"
---
# <a name="rightsenum"></a>RightsEnum

**适用于**： Access 2013、 Office 2013

指定组或用户对某个对象的权限。

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
<td><p><strong>adRightCreate</strong></p></td>
<td><p>16384<br />
(&amp;H4000)</p></td>
<td><p>用户或组拥有创建此类型的新对象的权限。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRightDelete</strong></p></td>
<td><p>65536<br />
(&amp;H10000)</p></td>
<td><p>用户或组拥有从对象删除数据的权限。对于 <strong>Tables</strong> 之类的对象，用户拥有从记录中删除数据值的权限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRightDrop</strong></p></td>
<td><p>256<br />
(&amp;H100)</p></td>
<td><p>用户或组拥有从目录移除对象的权限。例如，<strong>Tables</strong> 可通过 DROP TABLE SQL 命令删除。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRightExclusive</strong></p></td>
<td><p>512<br />
(&amp;H200)</p></td>
<td><p>用户或组拥有独占访问该对象的权限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRightExecute</strong></p></td>
<td><p>536870912<br />
(&amp;H20000000)</p></td>
<td><p>用户或组拥有执行该对象的权限。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRightFull</strong></p></td>
<td><p>268435456<br />
(&amp;H10000000)</p></td>
<td><p>用户或组拥有对该对象的全部权限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRightInsert</strong></p></td>
<td><p>32768<br />
(&amp;H8000)</p></td>
<td><p>用户或组拥有插入该对象的权限。对于 <strong>Table</strong> 之类的对象，用户拥有将数据插入表中的权限。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRightMaximumAllowed</strong></p></td>
<td><p>33554432 (&amp;h 2000000)</p></td>
<td><p>用户或组拥有提供程序所允许的最大数量的权限。特定权限与提供程序有关。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRightNone</strong></p></td>
<td><p>0</p></td>
<td><p>用户或组对该对象没有权限。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRightRead</strong></p></td>
<td><p>-2147483648<br />
(&amp;H 80000000)</p></td>
<td><p>用户或组拥有读取该对象的权限。对于 <a href="table-object-adox.md">Table</a> 之类的对象，用户拥有读取表中数据的权限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRightReadDesign</strong></p></td>
<td><p>1024<br />
(&amp;H400)</p></td>
<td><p>用户或组拥有读取该对象的设计的权限。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRightReadPermissions</strong></p></td>
<td><p>131072<br />
(&amp;H20000)</p></td>
<td><p>用户或组可查看目录中某个对象的特定权限，但是不能更改。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRightReference</strong></p></td>
<td><p>8192<br />
(&amp;H2000)</p></td>
<td><p>用户或组拥有引用该对象的权限。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRightUpdate</strong></p></td>
<td><p>1073741824<br />
(&amp;H40000000)</p></td>
<td><p>用户或组拥有更新该对象的权限。对于 <strong>Table</strong> 之类的对象，用户拥有更新表中数据的权限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRightWithGrant</strong></p></td>
<td><p>4096<br />
(&amp;H1000)</p></td>
<td><p>用户或组有权将对该对象的权限授予他人。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRightWriteDesign</strong></p></td>
<td><p>2048<br />
(&amp;H800)</p></td>
<td><p>用户或组拥有更新该对象的设计的权限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adRightWriteOwner</strong></p></td>
<td><p>524288<br />
(&amp;H80000)</p></td>
<td><p>用户或组拥有修改该对象的所有者的权限。</p></td>
</tr>
<tr class="even">
<td><p><strong>adRightWritePermissions</strong></p></td>
<td><p>262144<br />
(&amp;H40000)</p></td>
<td><p>用户或组可修改目录中某个对象的特定权限。</p></td>
</tr>
</tbody>
</table>

