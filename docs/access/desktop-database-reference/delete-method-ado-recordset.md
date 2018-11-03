---
title: Delete 方法（ADO 记录集）
TOCTitle: Delete method (ADO Recordset)
ms:assetid: 62c39b4d-223e-7b48-6780-6cd272e3114e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249374(v=office.15)
ms:contentKeyID: 48545246
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 324366ef1fb399bf4a6b31113a288fa1abdc6b2b
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947278"
---
# <a name="delete-method-ado-recordset"></a>Delete 方法（ADO 记录集）


**适用于**： Access 2013、 Office 2013



用于删除当前记录或一组记录。

## <a name="syntax"></a>语法

*记录集*。删除*AffectRecords*

## <a name="parameters"></a>参数

- *AffectRecords*

  - [AffectEnum](affectenum.md) 值，可确定 **Delete** 方法将影响的记录数。默认值为 **adAffectCurrent** 。


> [!NOTE]
> [!注释] **adAffectAll** 和 **adAffectAllChapters** 不是有效的 **Delete** 参数。

## <a name="remarks"></a>备注

使用 **Delete** 方法可为 [Recordset](recordset-object-ado.md) 对象中的当前记录或记录组打上删除标记。如果 **Recordset** 对象不允许删除记录，则会发生错误。在即时更新模式下，会立即在数据库中进行删除。如果无法顺利删除记录（例如，由于违反数据库完整性），在调用 **Update** 后，该记录仍保持为编辑模式。这意味着在从当前记录移开（例如，用 [Close](cancelupdate-method-ado.md)、[Move](close-method-ado.md) 或 [NextRecordset](move-method-ado.md)）之前，必须使用 [CancelUpdate](nextrecordset-method-ado.md) 取消更新。

如果处于批更新模式下，则会将记录标记为从缓存中删除，而在调用 [UpdateBatch](updatebatch-method-ado.md) 方法时执行实际的删除操作。（可以使用 [Filter](filter-property-ado.md) 属性查看删除的记录。）

检索已删除记录中的字段值时会产生错误。删除当前记录后，在移动到其他记录之前，已删除记录仍然是当前记录。一旦从已删除记录移开，就无法再访问它。

如果在事务中嵌套删除，可以使用 [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法恢复已删除的记录。处于批更新模式时，可以使用 [CancelBatch](cancelbatch-method-ado.md) 方法取消一个或一组挂起的删除操作。

如果由于与基础数据冲突而导致删除记录的尝试失败（例如，记录已被另一个用户删除），则提供程序会将警告返回到 [Errors](errors-collection-ado.md) 集合，但是不会停止程序执行。只有当所有被请求的记录都有冲突时，才会发生运行时错误。

如果设置了 [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 动态属性，且 **Recordset** 是对多个表执行 JOIN 操作的结果，那么 **Delete** 方法将只从 [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 属性所指定的表中删除行。

