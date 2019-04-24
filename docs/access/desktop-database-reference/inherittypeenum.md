---
title: InheritTypeEnum (Access desktop database reference)
TOCTitle: InheritTypeEnum
ms:assetid: aa505c66-5871-10a8-35a7-cb30bb5dc21a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249787(v=office.15)
ms:contentKeyID: 48546944
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ba1a78e49d44bce0c489e4f5259ec9699543e231
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291412"
---
# <a name="inherittypeenum"></a>InheritTypeEnum

**适用于**：Access 2013、Office 2013

指定对象将如何继承通过 [SetPermissions](setpermissions-method-adox.md) 设置的权限。

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
<td><p><strong>adInheritBoth</strong></p></td>
<td><p>第三章</p></td>
<td><p>主对象包含的对象和其他容器继承该项。</p></td>
</tr>
<tr class="even">
<td><p><strong>adInheritContainers</strong></p></td>
<td><p>双面</p></td>
<td><p>主对象包含的其他容器继承该项。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adInheritNone</strong></p></td>
<td><p>0</p></td>
<td><p>默认值。不发生继承。</p></td>
</tr>
<tr class="even">
<td><p><strong>adInheritNoPropagate</strong></p></td>
<td><p>4</p></td>
<td><p><strong>adInheritObjects</strong> 和 <strong>adInheritContainers</strong> 标志不传播到继承的项。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adInheritObjects</strong></p></td>
<td><p>1</p></td>
<td><p>容器中的非容器对象继承权限。</p></td>
</tr>
</tbody>
</table>

