---
title: Recordset2.BOF 属性 (DAO)
TOCTitle: BOF Property
ms:assetid: d97d0507-0d5a-e3f1-fa30-40caec9f3ffa
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835098(v=office.15)
ms:contentKeyID: 48548053
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8ee64cbdea3a17f00939041f808ae6261d9810ae
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919638"
---
# <a name="recordset2bof-property-dao"></a>Recordset2.BOF 属性 (DAO)


**适用于**： Access 2013、 Office 2013

返回一个值，该值指示当前记录的位置是否在 **Recordset** 对象中的第一条记录之前。只读 **Boolean** 类型。

## <a name="syntax"></a>语法

*表达式*。BOF

*表达式*一个表示**Recordset2**对象的变量。

## <a name="remarks"></a>注解

可以使用 **BOF** 和 **EOF** 属性确定 **Recordset** 对象是否包含记录，或确定在从一条记录移动到另一条记录时是否超出了 **Recordset** 对象的限制。

当前记录指针的位置决定了 **BOF** 和 **EOF** 返回值。

如果 **BOF** 或 **EOF** 属性为 **True**，则没有当前记录。

如果打开的 **Recordset** 对象不包含记录，则 **BOF** 和 **EOF** 属性设置为 **True**，且 **Recordset** 对象的 **RecordCount** 属性设置为 0。当打开的 **Recordset** 对象至少包含一条记录时，则第一条记录即是当前记录， **BOF** 和 **EOF** 属性都为 **False**；它们一直保持 **False**，直到您分别使用 **MovePrevious** 或 **MoveNext** 方法移动到 **Recordset** 对象的开头和末尾之外为止。如果您移动到 Recordset 的开头或末尾之外的位置，则没有当前记录或不存在记录。

如果删除了 **Recordset** 对象中剩下的最后一条记录，则在尝试重新定位当前记录之前， **BOF** 和 **EOF** 属性都会保持为 **False**。

如果对包含记录的 **Recordset** 对象使用 **MoveLast** 方法，则最后一条记录将成为当前记录；如果之后又使用 **MoveNext** 方法，则当前记录将变为无效， **EOF** 属性设置为 **True**。相反，如果对包含记录的 **Recordset** 对象使用 **MoveFirst** 方法，则第一条记录将成为当前记录；如果之后又使用 **MovePrevious** 方法，则没有当前记录， **BOF** 属性设置为 **True**。

通常，在处理 **Recordset** 对象中的所有记录时，代码将使用 **MoveNext** 方法遍历所有记录，直到 **EOF** 属性设置为 **True** 为止。

如果在 **EOF** 属性设置为 **True** 的情况下使用 **MoveNext** 方法，或者在 **BOF** 属性设置为 **True** 的情况下使用 **MovePrevious** 方法，则会发生错误。

下表显示了在使用不同的 **BOF** 和 **EOF** 属性组合时允许的 Move 方法。

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
<th><p>MoveFirst，<br />
MoveLast</p></th>
<th><p>MovePrevious、<br />
移动&lt;0</p></th>
<th><p><br />
Move 0</p></th>
<th><p>MoveNext、<br />
移动&gt;0</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>BOF = true，则</strong><br />
<strong>EOF = False</strong></p></td>
<td><p>允许</p></td>
<td><p>错误</p></td>
<td><p>错误</p></td>
<td><p>允许</p></td>
</tr>
<tr class="even">
<td><p><strong>BOF = False，</strong><br />
<strong>EOF = True</strong></p></td>
<td><p>允许</p></td>
<td><p>允许</p></td>
<td><p>错误</p></td>
<td><p>错误</p></td>
</tr>
<tr class="odd">
<td><p>均为 <strong>True</strong></p></td>
<td><p>错误</p></td>
<td><p>错误</p></td>
<td><p>错误</p></td>
<td><p>错误</p></td>
</tr>
<tr class="even">
<td><p>均为 <strong>False</strong></p></td>
<td><p>允许</p></td>
<td><p>允许</p></td>
<td><p>允许</p></td>
<td><p>允许</p></td>
</tr>
</tbody>
</table>


允许 Move 方法并不意味着该方法可以成功定位记录。它只是表示允许尝试执行指定的 Move 方法，且不会生成错误。在尝试 Move 后， **BOF** 和 **EOF** 属性的状态可能更改。

**OpenRecordset** 方法在内部调用 **MoveFirst** 方法。因此，对空记录集使用 **OpenRecordset** 方法会将 **BOF** 和 **EOF** 属性设置为 **True**。（有关失败的 **MoveFirst** 方法的行为，请参阅下表。）

所有成功定位记录的 Move 方法都会将 **BOF** 和 **EOF** 均设置为 **False**。

在 Microsoft Access 工作区中，如果向空 Recordset 添加记录， **BOF** 将成为 **False**，但是 **EOF** 将保持 **True**，指示当前位置位于 Recordset 的末尾。

任何 **Delete** 方法都不会更改 **BOF** 或 **EOF** 属性的设置，即使它从记录集删除了唯一的剩余记录也是如此。

下表显示不定位记录的 Move 方法如何影响 **BOF** 和 **EOF** 属性设置。

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
<td><p><strong>MoveFirst</strong> <strong>MoveLast</strong></p></td>
<td><p><strong>True</strong></p></td>
<td><p><strong>True</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Move</strong> 0</p></td>
<td><p>没有变化</p></td>
<td><p>没有变化</p></td>
</tr>
<tr class="odd">
<td><p><strong>MovePrevious</strong>、<strong>移动</strong> &lt; 0</p></td>
<td><p><strong>True</strong></p></td>
<td><p>没有变化</p></td>
</tr>
<tr class="even">
<td><p><strong>MoveNext</strong>、<strong>移动</strong> &gt; 0</p></td>
<td><p>没有变化</p></td>
<td><p><strong>True</strong></p></td>
</tr>
</tbody>
</table>

