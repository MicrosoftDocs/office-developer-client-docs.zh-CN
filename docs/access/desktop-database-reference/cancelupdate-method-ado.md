---
title: CancelUpdate 方法 (ADO)
TOCTitle: CancelUpdate Method (ADO)
ms:assetid: 2bd4d168-ba52-7786-5046-44febeda88e1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249065(v=office.15)
ms:contentKeyID: 48543938
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c56d8fc7eaab7989eaa967aa90090ad59c1656dc
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884763"
---
# <a name="cancelupdate-method-ado"></a>CancelUpdate 方法 (ADO)


**适用于**： Access 2013、 Office 2013

在调用 [Update](recordset-object-ado.md) 方法之前，取消对 [Recordset](fields-collection-ado.md) 对象的当前行或新行，或对 [Record](record-object-ado.md) 对象的 [Fields](update-method-ado.md) 集合所做的任何更改。

## <a name="syntax"></a>语法

*记录集*。CancelUpdate

*记录*。*字段*。CancelUpdate

## <a name="remarks"></a>说明

**Recordset**

可以使用 **CancelUpdate** 方法取消对当前行所做的任何更改或放弃新添加的行。但调用 **Update** 方法之后，便无法取消对当前行或新行所做的更改，除非更改是可以用 [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法回滚的事务的一部分或批更新的一部分。在批更新情况下，可以用 **CancelUpdate** 或 **CancelBatch** 方法取消 [Update](cancelbatch-method-ado.md) 。

如果调用 **CancelUpdate** 方法时正在添加新行，则当前行将变成调用 [AddNew](addnew-method-ado.md) 之前的当前行。

如果正处于编辑模式下，并希望离开当前记录（例如，用 [Move](move-method-ado.md)、[NextRecordset](nextrecordset-method-ado.md) 或 [Close](close-method-ado.md)），那么可以使用 **CancelUpdate** 取消任何挂起的更改。如果更新无法成功发布到数据源，则可能需要执行以上操作（例如，如果删除尝试由于违反了参照完整性而失败，则在调用 **Delete** 之后将离开处于编辑模式下的 [Recordset](delete-method-ado-recordset.md) ）。

**Record**

可以使用 **CancelUpdate** 方法取消 [Field](field-object-ado.md) 对象的任何挂起的插入或删除，以及取消现有字段的挂起更新并将其还原为原来的值。 [Fields](status-property-ado-recordset.md) 集合中所有字段的 **Status** 属性均设置为 **adFieldOK** 。

