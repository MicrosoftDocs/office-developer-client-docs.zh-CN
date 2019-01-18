---
title: Recordset.MoveLast 方法 (DAO)
TOCTitle: MoveLast method
ms:assetid: fc0f7a33-1f55-9f5b-b00d-1b81f49b1c3e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837192(v=office.15)
ms:contentKeyID: 48548881
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 79799742499e163a43d51a2d8553adcadf27b36d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715268"
---
# <a name="recordsetmovelast-method-dao"></a>Recordset.MoveLast 方法 (DAO)

**适用于**： Access 2013、 Office 2013

移到指定的 **Recordset** 对象中的最后一条记录，并使该记录成为当前记录。

## <a name="syntax"></a>语法

*表达式*。MoveLast （***选项***）

*表达式*一个表示**Recordset**对象的变量。

## <a name="parameters"></a>Parameters

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Options</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>设置为 <strong>dbRunAsync</strong> 可异步运行对 <strong>MoveLast</strong> 的调用。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

使用 **Move** 方法可以在记录间移动，而不需要应用条件。

如果要编辑当前记录，请确保使用 **Update** 方法保存更改，然后移到另一条记录。如果在不更新的情况下移到另一条记录，则更改将会丢失，且不发出警告。

在打开 **Recordset** 时，第一条记录将是当前记录，并且 **BOF** 属性为 **False**。如果 **Recordset** 不包含记录，则 **BOF** 属性为 **True**，并且不存在当前记录。

如果在使用 **MoveFirst** 或 **MoveLast** 时，第一条或最后一条记录已经是当前记录，则当前记录不会更改。

如果 recordset 引用表类型**Recordset** （仅限 Microsoft Access 工作区），则移动遵循当前索引。 可以使用 **Index** 属性设置当前索引。 如果不设置当前索引，则返回记录的顺序将是不确定的。

> [!NOTE]
> [!注释] 可使用 **MoveLast** 方法完全填充动态集类型或快照集类型的 **Recordset**，以便在 **Recordset** 中提供当前的记录数。 但是，如果以这种方式使用 **MoveLast**，可能会减慢应用程序的性能。 如果绝对有必要获取有关最近打开的 **Recordset** 的准确记录计数，只应使用 **MoveLast** 获取记录计数。 
> 
> 如果将 **dbRunAsync** 常量用于 **MoveLast**，则方法调用是异步的。 可以使用 **StillExecuting** 属性确定何时完全填充了 **Recordset**，并可使用 **Cancel** 方法终止执行异步的 **MoveLast** 方法调用。

不能对仅向前类型**Recordset**对象使用**MoveFirst**、 **MoveLast**和**MovePrevious**方法。

若要将 **Recordset** 对象中的当前记录的位置向前或向后移动指定的记录数，请使用 **Move** 方法。

