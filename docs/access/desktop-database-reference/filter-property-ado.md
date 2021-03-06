---
description: Filter 属性
title: 'ADO (筛选器) '
TOCTitle: Filter property (ADO)
ms:assetid: 5abc528a-a6ee-34de-5d44-a3249194b0a0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249314(v=office.15)
ms:contentKeyID: 48545053
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9d3234f1d5f41fd9f07b8d98bf3df395067780ae
ms.sourcegitcommit: 0419850d5c1b3439d9da59070201fb4952ca5d07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734194"
---
# <a name="filter-property-ado"></a>ADO (筛选器) 


**适用于**：Access 2013、Office 2013

指示 [Recordset](recordset-object-ado.md) 中数据的筛选条件。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Variant** 值，该值可包含以下内容之一：

  - **条件字符串**  由一个或多个用 **AND** 或 **OR** 运算符连接的子句组成的字符串。

  - **书签数组**  指向 **Recordset** 对象中的记录的唯一书签值数组。

  - 一个 [FilterGroupEnum](filtergroupenum.md) 值。

## <a name="remarks"></a>备注

使用 **Filter** 属性可以有选择地屏蔽 **Recordset** 对象中的记录。经过筛选的 **Recordset** 成为当前游标。这将影响基于当前游标返回值的其他属性，如 [AbsolutePosition](absoluteposition-property-ado.md)、[AbsolutePage](absolutepage-property-ado.md)、[RecordCount](recordcount-property-ado.md) 和 [PageCount](pagecount-property-ado.md)。因为将 **Filter** 属性设置为特定值将移动当前记录使其成为满足新值的第一条记录。

条件字符串由 *FieldName-Operator-Value* 格式的子句组成 (例如，"LastName = 'Smith'") 。 您可以通过将单个子句与 **AND** (（例如，"LastName = 'Smith' AND FirstName = 'John'") 或 **OR** (例如，") ）连接来创建复合子句。 您可以通过将单个子句与 **AND** (连接来创建复合子句，例如，"LastName = 'Smith' AND FirstName = 'John'") 或 **OR** (例如，"LastName = 'Smith' OR LastName = 'Jones'") 。 条件字符串的使用准则如下：

  - *FieldName* 必须是 **Recordset** 中的有效字段名。如果字段名中包含空格，则必须用方括号将字段名括起来。

  - *运算符* 必须是下列值之一 \<, \> ：、=、= \<=, \> \<\> 或 **LIKE。**

  - *值* 是您将与之比较字段值的值 (例如，"Smith"、8/24/95、12.345 或 \# \# $50.00) 。 将单引号与字符串和井号 \# () 日期。 对于数字，可以使用小数点、美元符和科学记数法。 如果 *Operator* 为 **LIKE**，则 *Value* 可以使用通配符。 仅允许使用星号 () 百分号 (%) 通配符，并且它们必须是字符串中的最后一 \* 个字符。 *Value* 不能为空。

    > [!NOTE]
    > [!注释] 若要在筛选值中包含单引号 (')，则用两个单引号表示一个单引号。例如，若要筛选 O'Malley，则条件字符串应为 "col1 = 'O''Malley'"。若要在筛选值的开始和末尾均包含单引号，则使用井号 (#) 包围该字符串。例如，若要筛选 '1'，则条件字符串应为 "col1 = #'1'#"。

-   **AND** 和 **OR** 之间并没有优先级的区别。 可以使用圆括号将子句分组。 但是，不能将 **OR** 联接的子句分组，然后使用 **AND** 将组加入另一个子句，如下面的代码片段所示：  
 `(LastName = 'Smith' OR LastName = 'Jones') AND FirstName = 'John'`  
  
-   可以按如下方法构造此筛选条件  
 `(LastName = 'Smith' AND FirstName = 'John') OR (LastName = 'Jones' AND FirstName = 'John')`  

  - 在 **LIKE** 子句中，可以在模式开头和结尾使用通配符 (例如 LastName Like ' mit ') ，或仅在模式 (的末尾使用通配符，例如 \* \* ，LastName Like 'Smit \* ') 。

通过仅允许查看，例如仅允许查看上次调用 [UpdateBatch](updatebatch-method-ado.md) 方法的过程中涉及到的记录，筛选常量更便于解决批更新模式中的各个记录冲突。

如果与基础数据冲突（例如，其他用户已经删除该记录），则不能成功设置 **Filter** 属性本身。此时，提供程序将向 [Errors](errors-collection-ado.md) 集合返回警告，但不会中断程序执行。只有所有请求的记录均存在冲突时才会产生运行时错误。使用 [Status](status-property-ado-recordset.md) 属性可定位发生冲突的记录。

将 **Filter** 属性设置为零长度字符串 ("") 与使用 **adFilterNone** 常量具有相同效果。

一旦设置了 **Filter** 属性，当前记录位置就会移至 **Recordset** 中已筛选记录子集的首条记录。同样，如果清除 **Filter** 属性，则当前记录位置将移至 **Recordset** 中的首条记录。

有关可与 [Filter](bookmark-property-ado.md) 属性一起用来生成数组的书签值的说明，请参阅 **Bookmark** 属性。

只有 **条件** 字符串格式的筛选器 (例如 OrderDate \> '12/31/1999') 影响持久 **记录集的内容**。 通过 **Bookmark** 数组或使用 **FilterGroupEnum** 中的值创建的 **Filter** 不会影响持久 Recordset 的内容。 这些规则适用于通过客户端或服务器端游标创建的 **Recordset** 。

> [!NOTE]
> [!注释] 在批更新模式下，将 **adFilterPendingRecords** 标记应用于筛选和修改的 **Recordset** 时，如果筛选是基于单键表的键字段并且对该键字段值进行修改，则得到的 **Recordset** 将为空。如果满足以下条件之一，得到的 **Recordset** 就不为空：
> - 基于单键表中的非键字段的筛选。
> - 基于多键表中的任何字段的筛选。
> - 对单键表中的非键字段进行修改。
> - 对多键表中的任何字段进行修改。

下表总结了在不同的筛选和修改方式组合下 **adFilterPendingRecords** 所产生的效果。左边的列显示的是可能的修改方式：可对任何非键字段、单键表中的键字段、或多键表中的任何键字段进行修改。最上面的行显示的是筛选条件：可以根据任何非键字段、单键表中的键字段、或多键表中的任何键字段进行筛选。交叉单元显示的是结果：+ 表示使用 **adFilterPendingRecords** 产生非空 **Recordset** ； **-** 表示空 **Recordset** 。

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><br />
</p></th>
<th><p>非键</p></th>
<th><p>单键</p></th>
<th><p>多键</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>非键</p></td>
<td><p>+</p></td>
<td><p>+</p></td>
<td><p>+</p></td>
</tr>
<tr class="even">
<td><p>单键</p></td>
<td><p>+</p></td>
<td><p>-</p></td>
<td><p>无</p></td>
</tr>
<tr class="odd">
<td><p>多键</p></td>
<td><p>+</p></td>
<td><p>不适用</p></td>
<td><p>+</p></td>
</tr>
</tbody>
</table>

