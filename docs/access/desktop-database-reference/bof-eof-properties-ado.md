---
title: BOF、EOF 属性 (ADO)
TOCTitle: BOF, EOF properties (ADO)
ms:assetid: f797e140-5572-1a4d-9afc-285f6a3868a8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250260(v=office.15)
ms:contentKeyID: 48548768
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d36a65ce8a6808f2128749bd7fbc6e468acbd279
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296785"
---
# <a name="bof-eof-properties-ado"></a>BOF、EOF 属性 (ADO)


**适用于**：Access 2013、Office 2013

**BOF**  指示当前记录位置在 [Recordset](recordset-object-ado.md) 对象中的第一条记录之前。

**EOF**  指示当前记录位置在 **Recordset** 对象中的最后一条记录之后。

## <a name="return-value"></a>返回值

**BOF** 和 **EOF** 属性将返回 **Boolean** 值。

## <a name="remarks"></a>注解

使用 **BOF** 和 **EOF** 属性可以确定 **Recordset** 对象是否包含记录，或确定在从一条记录移动到另一条记录时是否超出了 **Recordset** 对象的限制。

如果当前记录位于第一个记录之前，则 **BOF** 属性返回 **True** (-1)，如果当前记录就是第一个记录或者位于第一个记录之后，则返回 **False** (0)。

如果当前记录位于最后一个记录之后，则 **EOF** 属性返回 **True** ，如果当前记录就是最后一个记录或者位于最后一个记录之前，则返回 **False** 。

如果 **BOF** 或 **EOF** 属性为 **True**，则没有当前记录。

如果打开不包含任何记录的 **Recordset** 对象，**BOF** 和 **EOF** 属性都会设置为 **True**（有关 **Recordset** 的此状态的详细信息，请参阅 [RecordCount](recordcount-property-ado.md) 属性）。当打开至少包含一条记录的 **Recordset** 对象时，第一条记录为当前记录，且 **BOF** 和 **EOF** 属性均为 **False**。

如果删除了 **Recordset** 对象中剩下的最后一条记录，则在尝试重新定位当前记录之前， **BOF** 和 **EOF** 属性都会保持为 **False** 。

下表显示了在使用不同的 **BOF** 和 **EOF** 属性组合时允许的 **Move** 方法。

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p>MoveFirst<br />
MoveLast</p></th>
<th><p>MovePrevious<br />
移动&lt; 0</p></th>
<th><p><br />
Move 0</p></th>
<th><p>MoveNext<br />
移动&gt; 0</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>BOF = True,</strong><br />
<strong>EOF = False</strong></p></td>
<td><p>Allowed</p></td>
<td><p>Error</p></td>
<td><p>Error</p></td>
<td><p>Allowed</p></td>
</tr>
<tr class="even">
<td><p><strong>BOF = False,</strong><br />
<strong>EOF = True</strong></p></td>
<td><p>Allowed</p></td>
<td><p>Allowed</p></td>
<td><p>Error</p></td>
<td><p>Error</p></td>
</tr>
<tr class="odd">
<td><p>均为 <strong>True</strong></p></td>
<td><p>错误</p></td>
<td><p>Error</p></td>
<td><p>Error</p></td>
<td><p>错误</p></td>
</tr>
<tr class="even">
<td><p>均为 <strong>False</strong></p></td>
<td><p>允许</p></td>
<td><p>Allowed</p></td>
<td><p>Allowed</p></td>
<td><p>允许</p></td>
</tr>
</tbody>
</table>


允许某个 **Move** 方法并不保证该方法将成功地定位到一条记录；这仅意味着调用指定的 **Move** 方法不会生成错误。

下表显示了在调用各种 **Move** 方法但不能成功定位到记录时，**BOF** 和 **EOF** 属性的设置会发生什么变化。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p>BOF</p></th>
<th><p>EOF</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>MoveFirst</strong>、 <strong>MoveLast</strong></p></td>
<td><p>设置为 <strong>True</strong></p></td>
<td><p>设置为 <strong>True</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Move</strong> 0</p></td>
<td><p>没有变化</p></td>
<td><p>没有变化</p></td>
</tr>
<tr class="odd">
<td><p><strong>MovePrevious</strong>,<strong>移动</strong> &lt; 0</p></td>
<td><p>设置为 <strong>True</strong></p></td>
<td><p>没有变化</p></td>
</tr>
<tr class="even">
<td><p><strong>MoveNext</strong>,<strong>移动</strong> &gt; 0</p></td>
<td><p>没有变化</p></td>
<td><p>设置为 <strong>True</strong></p></td>
</tr>
</tbody>
</table>

