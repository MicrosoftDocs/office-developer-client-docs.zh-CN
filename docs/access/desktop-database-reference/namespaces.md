---
title: 命名空间 （访问桌面数据库参考 （英文）
TOCTitle: Namespaces
ms:assetid: e39f003c-3d16-1fae-48c5-304593c41f2f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250158(v=office.15)
ms:contentKeyID: 48548318
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a5fb61c02a5679c6fd63e9d5dd2a257ab5f7d96a
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25996466"
---
# <a name="namespaces"></a>命名空间

**适用于**： Access 2013、 Office 2013

ADO 中的 XML 持久化格式使用以下四个命名空间。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>前缀</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>s</p></td>
<td><p>指的是&quot;XML 数据&quot;命名空间包含的元素和属性的定义当前<strong>Recordset</strong>的架构。</p></td>
</tr>
<tr class="even">
<td><p>dt</p></td>
<td><p>指的是数据类型定义规范。</p></td>
</tr>
<tr class="odd">
<td><p>rs</p></td>
<td><p>指的是命名空间，该命名空间包含特定于 ADO <strong>Recordset</strong> 属性和特性的元素和特性。</p></td>
</tr>
<tr class="even">
<td><p>z</p></td>
<td><p>指的是当前行集的架构。</p></td>
</tr>
</tbody>
</table>


客户端不应当向这些命名空间添加它自己的标记，因为它们是由规格定义的。例如，客户端不应当将命名空间定义为"urn:schemas-microsoft-com:rowset"，然后写出诸如"rs:MyOwnTag"这样的内容。若要详细了解命名空间，请参阅 [XML 命名空间](https://www.w3.org/tr/xml-names/)。

> [!NOTE]
> [!注释] 架构标记的 ID 必须是"RowsetSchema"，并且用来引用当前行集架构的命名空间必须指向"#RowsetSchema"。

注意，命名空间的前缀（即冒号右侧和等号左侧的部分）是任意的。

```vb 
 
xmlns:rs="urn:schemas-microsoft-com:rowset" 
```

用户可以将它定义为任何名称，只要在整个 XML 文档中都一致地使用此名称。ADO 始终写出"s"、"rs"、"dt"和"z"，但这些前缀名称不会硬编码到加载组件中。



