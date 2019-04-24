---
title: Index 属性 (ADO)
TOCTitle: Index property (ADO)
ms:assetid: 4cc00521-dcb4-19b2-2174-6e0e9bd42e62
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249241(v=office.15)
ms:contentKeyID: 48544715
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7d436ec9102c4c75688b6c6ac973ca85e8c280d0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291704"
---
# <a name="index-property-ado"></a>Index 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示当前对 [Recordset](recordset-object-ado.md) 对象有效的索引的名称。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **String** 值，该值为索引名称。

## <a name="remarks"></a>注解

由 **Index** 属性命名的索引必须事先已经在 **Recordset** 对象的基本表上进行声明。即索引必须已在程序中声明为 ADOX [Index](index-object-adox.md) 对象，或在创建基本表时声明。

如果无法设置索引，则会发生运行时错误。以下情况下无法设置 **Index** 属性：

  - 在 [WillChangeRecordset](willchangerecordset-and-recordsetchangecomplete-events-ado.md) 或 **RecordsetChangeComplete** 事件处理程序中。

  - 如果 **Recordset** 仍在执行某个操作（可由 [State](state-property-ado.md) 属性确定）。

  - 如果已通过 **Filter** 属性在 [Recordset](filter-property-ado.md) 上设置了筛选器。

如果关闭了 **Recordset** ，则始终能够成功设置 **Index** 属性，但是如果基础提供程序不支持索引，则 **Recordset** 将无法成功打开，或索引将无法使用。

如果可以设置索引，则可以更改当前行位置。这将会导致 [AbsolutePosition](absoluteposition-property-ado.md) 属性的更新，并会导致生成 **WillChangeRecordset** 、 **RecordsetChangeComplete** 、 [WillMove](willmove-and-movecomplete-events-ado.md) 和 [MoveComplete](willmove-and-movecomplete-events-ado.md) 事件。

如果可以设置索引且 [LockType](locktype-property-ado.md) 属性为 **adLockPessimistic** 或 **adLockOptimistic** ，则将执行隐式 [UpdateBatch](updatebatch-method-ado.md) 操作。这将释放当前组和受影响的组，并释放任何现有的筛选，同时当前行位置将移至重新排序的 **Recordset** 的首行。

**Index** 属性与 [Seek](seek-method-ado.md) 方法一起使用。 如果基础提供程序不支持**Index**属性, 因此使用**Seek**方法, 请考虑改用[Find](find-method-ado.md)方法。 确定**Recordset**对象是否支持使用[支持](supports-method-ado.md)**(adIndex)** 方法的索引。

尽管二者均处理索引，但内置 **Index** 属性与动态 [Optimize](optimize-property-dynamic-ado.md) 属性无关。

