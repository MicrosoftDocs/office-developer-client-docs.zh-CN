---
title: Status 属性 (ADO Recordset)
TOCTitle: Status Property (ADO Recordset)
ms:assetid: bf3ccb36-c985-5fae-4f76-c48a0e20e6f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249930(v=office.15)
ms:contentKeyID: 48547482
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1979ad721a01ef72c08da1531a8826ec320915e5
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25604615"
---
# <a name="status-property-ado-recordset"></a>Status 属性 (ADO Recordset)


**适用于**： Access 2013 |Office 2013

指示与批更新或其他批量操作相关的当前记录的状态。

<<<<<<< 标头
## <a name="return-value"></a>返回值
=======
## <a name="return-value"></a>返回值
>>>>>>> master

返回一个或多个 [RecordStatusEnum](recordstatusenum.md) 值的总和。

## <a name="remarks"></a>备注

使用 **Status** 属性可查看在批更新期间修改的记录有哪些更改被挂起。也可使用 **Status** 属性查看执行大量操作时失败的记录的状态。例如，调用 [Recordset](resync-method-ado.md) 对象的 [Resync](updatebatch-method-ado.md)、[UpdateBatch](cancelbatch-method-ado.md) 或 [CancelBatch](recordset-object-ado.md) 方法，或者将 [Recordset](filter-property-ado.md) 对象的 **Filter** 属性设置为书签数组。使用此属性，可确定指定记录失败的原因，并据此将问题解决。

