---
title: Status 属性（ADO 记录集）
TOCTitle: Status property (ADO Recordset)
ms:assetid: bf3ccb36-c985-5fae-4f76-c48a0e20e6f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249930(v=office.15)
ms:contentKeyID: 48547482
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4017ff216c17479a69d6d07d0abe51b30fd5e680
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308517"
---
# <a name="status-property-ado-recordset"></a>Status 属性（ADO 记录集）


**适用于**：Access 2013、Office 2013

指示与批更新或其他批量操作相关的当前记录的状态。

## <a name="return-value"></a>返回值

返回一个或多个 [RecordStatusEnum](recordstatusenum.md) 值的总和。

## <a name="remarks"></a>注解

使用 **Status**  属性可查看在批更新期间修改的记录有哪些更改被挂起。也可使用 **Status** 属性查看执行大量操作时失败的记录的状态。例如，调用 [Recordset](recordset-object-ado.md) 对象的 [Resync](resync-method-ado.md)、[UpdateBatch](updatebatch-method-ado.md) 或 [CancelBatch](cancelbatch-method-ado.md) 方法，或者将 **Recordset** 对象的 [Filter](filter-property-ado.md) 属性设置为书签数组。使用此属性，可确定指定记录失败的原因，并据此将问题解决。

