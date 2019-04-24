---
title: Cell 对象 (ADO MD)
TOCTitle: Cell object (ADO MD)
ms:assetid: b9d00b71-1f40-5bd1-4b89-fbdb59c552ba
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249892(v=office.15)
ms:contentKeyID: 48547356
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7bb2a479789a8c5bd1825b6cb04e602e0b829dfb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296547"
---
# <a name="cell-object-ado-md"></a>Cell 对象 (ADO MD)


**适用于**：Access 2013、Office 2013

代表处于单元格集中包含的坐标轴交点处的数据。

## <a name="remarks"></a>注解

**Cell** 对象由 [Cellset](cellset-object-ado-md.md) 对象的 [Item](item-property-ado-md-cellset.md) 属性返回。

使用 **Cell** 对象的集合和属性，可以执行下列操作：

- 使用 **Value** 属性返回 [Cell](value-property-ado-md.md) 中的数据。

- 使用 **FormattedValue** 属性返回代表 [Value](formattedvalue-property-ado-md.md) 属性的带格式显示的字符串。

- 使用 **Ordinal** 属性返回 **Cellset** 中的 [Cell](ordinal-property-ado-md-cell.md) 的序号值。

- 使用 **Positions** 集合确定 [CubeDef](cubedef-object-ado-md.md) 中的 [Cell](positions-collection-ado-md.md) 的位置。

- 使用标准 ADO **Properties** 集合检索有关 [Cell](properties-collection-ado.md) 的其他信息。

**Properties** 集合包含提供程序提供的属性。下表列出了可能可用的属性。实际的属性列表可能有所不同，具体取决于提供程序的实现。有关可用属性的更完整列表，请参阅提供程序文档。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BackColor</p></td>
<td><p>显示单元格时使用的背景色。</p></td>
</tr>
<tr class="even">
<td><p>FontFlags</p></td>
<td><p>详细描述应用于字体的效果的位掩码。</p></td>
</tr>
<tr class="odd">
<td><p>FontName</p></td>
<td><p>用于显示单元格值的字体。</p></td>
</tr>
<tr class="even">
<td><p>FontSize</p></td>
<td><p>用于显示单元格值的字号。</p></td>
</tr>
<tr class="odd">
<td><p>ForeColor</p></td>
<td><p>显示单元格时使用的前景色。</p></td>
</tr>
<tr class="even">
<td><p>FormatString</p></td>
<td><p>格式字符串中的值。</p></td>
</tr>
</tbody>
</table>

