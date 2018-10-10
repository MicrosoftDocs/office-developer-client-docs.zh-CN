---
title: 记录集的限制
TOCTitle: The Limits of a Recordset
ms:assetid: 51e27c95-e0c3-7fdc-ac11-891553620376
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249266(v=office.15)
ms:contentKeyID: 48544833
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e13e907c27fa6f764aae6ee499f0bd2854f9640b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465806"
---
# <a name="the-limits-of-a-recordset"></a>记录集的限制


**适用于**： Access 2013 |Office 2013

使用 **BOF** 和 **EOF** 属性，可以确定 **Recordset** 对象是否包含记录，或者在记录之间移动时是否超出了 **Recordset** 对象的限制。将 **BOF** 和 **EOF** 视为位于 **Recordset** 开头和末尾的"幻影"记录。基于 **检查数据**的示例 [Recordset](chapter-3-examining-data.md) 构建的对象如下所示：

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>ProductID</p></th>
<th><p>ProductName</p></th>
<th><p>单价</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BOF</p></td>
<td><p><br />
</p></td>
<td><p><br />
</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>海鲜粉</p></td>
<td><p>30.0000</p></td>
</tr>
<tr class="odd">
<td><p>14</p></td>
<td><p>沙茶</p></td>
<td><p>23.2500</p></td>
</tr>
<tr class="even">
<td><p>28</p></td>
<td><p>烤肉酱</p></td>
<td><p>45.6000</p></td>
</tr>
<tr class="odd">
<td><p>51</p></td>
<td><p>猪肉干</p></td>
<td><p>53.0000</p></td>
</tr>
<tr class="even">
<td><p>74</p></td>
<td><p>鸡精</p></td>
<td><p>10.0000</p></td>
</tr>
<tr class="odd">
<td><p>EOF</p></td>
<td><p><br />
</p></td>
<td><p><br />
</p></td>
</tr>
</tbody>
</table>


如果当前记录位于第一个记录之前，则 **BOF** 属性返回 **True** (-1)，如果当前记录就是第一个记录或者位于第一个记录之后，则返回 **False** (0)。

如果当前记录位于最后一个记录之后，则 **EOF** 属性返回 **True** ，如果当前记录就是最后一个记录或者位于最后一个记录之前，则返回 **False** 。

如果 **BOF** 或 **EOF** 属性为 **True** ，则说明当前无记录，如下面的代码所示：

```vb 
 
If oRs.BOF And oRs.EOF Then 
 ' Command returned no records. 
End If 
```

如果打开不包含任何记录的 **Recordset** 对象，则 **BOF** 和 **EOF** 属性均设置为 **True** ，而 **Recordset** 对象的 **RecordCount** 属性设置的值取决于游标的类型。 对于动态游标将返回-1 (**CursorType** = **adOpenDynamic**) 的其他游标，则返回 0。

如果打开至少包含一个记录的 **Recordset** 对象，则第一个记录是当前记录， **BOF** 和 **EOF** 属性均为 **False** 。

如果删除 **Recordset** 对象中最后一个剩余的记录，则游标将保留在未定状态。 **BOF** 和 **EOF** 属性可能一直保留在 **False** ，直到您尝试重新定位当前的记录，具体情况取决于提供程序。

