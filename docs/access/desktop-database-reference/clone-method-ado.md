---
title: Clone 方法-ActiveX 数据对象 (ADO)
TOCTitle: Clone method (ADO)
ms:assetid: ca9b2b76-90bf-9a60-2611-3cb4977d5591
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249984(v=office.15)
ms:contentKeyID: 48547693
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 095191bbfe55f2c38529cb1c260979c48dd2d5f1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28702962"
---
# <a name="clone-method-ado"></a>Clone 方法 (ADO)

**适用于**： Access 2013、 Office 2013

用于从现有 [Recordset](recordset-object-ado.md) 对象创建重复的 **Recordset** 对象。还可以指定克隆为只读状态。

## <a name="syntax"></a>语法

**设置***rstDuplicate* =  *rstOriginal*。克隆 (*LockType*)

## <a name="return-value"></a>返回值

返回 **Recordset** 对象引用。

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*rstDuplicate* |一个标识要创建的重复 **Recordset** 对象的对象变量。|
|*rstOriginal* |对象变量，用于标识要重复的 **Recordset** 对象。|
|*LockType* |可选。[LockTypeEnum](locktypeenum.md) 值，用于指定原始 **Recordset** 或只读 **Recordset** 的锁类型。有效值为 **adLockUnspecified** 或 **adLockReadOnly** 。|

## <a name="remarks"></a>说明

可以使用 **Clone** 方法创建多个重复的 **Recordset** 对象，尤其是要在给定记录集中保留多个当前记录时。使用 **Clone** 方法比采用与原始对象相同的定义创建和打开一个新的 **Recordset** 对象效率更高。

原始 [Recordset](filter-property-ado.md) 的 **Filter** 属性（如果有）不适用于克隆。可以为新的 **Recordset** 设置 **Filter** 属性，以筛选结果。要复制任何现有的 **Filter** 值，最简单的方法是直接为其赋值，如下所示：

新创建克隆的当前记录设置为第一条记录。

无论游标类型是什么，对一个 **Recordset** 对象所做的更改可以在该对象的所有副本中体现出来。但是，对原始 [Recordset](requery-method-ado.md) 对象执行 **Requery** 后，副本将不再与原始对象同步。

关闭原始 **Recordset** 不会关闭其副本，同样，关闭副本也不会关闭原始对象或其他任何副本。

只能克隆支持书签的 **Recordset** 对象。书签值是可以互换的；即，一个 **Recordset** 对象中的书签引用可以引用其任何副本中的同一个记录。

触发的某些 **Recordset** 事件也将在所有 **Recordset** 克隆中激发。不过，由于克隆的 **Recordset** 之间的当前记录不同，对于某些克隆而言事件可能无效。

例如，如果更改字段值，则在更改的 [Recordset](willchangefield-and-fieldchangecomplete-events-ado.md) 和所有克隆中都将发生 **WillChangeField** 事件。 （其中不进行更改） 克隆**Recordset**的**WillChangeField**事件的*字段*参数将只需引用克隆，这可能比当前另一条记录成为当前记录的字段的记录原始**Recordset**发生更改。

下表提供了所有 **Recordset** 事件的完整列表，并指示这些事件是否有效和对于用 **Clone** 方法生成的任何记录集克隆是否会触发这些事件。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>事件</p></th>
<th><p>是否在克隆中触发？</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="endofrecordset-event-ado.md">EndOfRecordset</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><a href="fetchcomplete-event-ado.md">FetchComplete</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><a href="fetchprogress-event-ado.md">FetchProgress</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><a href="willchangefield-and-fieldchangecomplete-events-ado.md">FieldChangeComplete</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="willmove-and-movecomplete-events-ado.md">MoveComplete</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><a href="willchangerecord-and-recordchangecomplete-events-ado.md">RecordChangeComplete</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">RecordsetChangeComplete</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><a href="willchangefield-and-fieldchangecomplete-events-ado.md">WillChangeField</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="willchangerecord-and-recordchangecomplete-events-ado.md">WillChangeRecord</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">在 WillChangeRecordset</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><a href="willmove-and-movecomplete-events-ado.md">WillMove</a></p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>

