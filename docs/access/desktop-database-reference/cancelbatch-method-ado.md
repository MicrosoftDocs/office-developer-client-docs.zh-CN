---
title: CancelBatch 方法 (ADO)
TOCTitle: CancelBatch method (ADO)
ms:assetid: be7bf073-ed0b-e24c-7ec0-b7379236782a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249925(v=office.15)
ms:contentKeyID: 48547463
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 832b367824fd8043486ff85f63739c3288696774
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296638"
---
# <a name="cancelbatch-method-ado"></a>CancelBatch 方法 (ADO)

**适用于**：Access 2013、Office 2013

用于取消挂起的批更新。

## <a name="syntax"></a>语法

*recordset*。CancelBatch *AffectRecords*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*AffectRecords* |可选。[AffectEnum](affectenum.md) 值，用于指示 **CancelBatch** 方法将影响的记录数。 |

## <a name="remarks"></a>注解

**CancelBatch** 方法用于取消处于批更新模式下的 [Recordset](recordset-object-ado.md) 中的任何挂起的更新。如果 **Recordset** 处于即时更新模式下，则调用无 **adAffectCurrent** 的 **CancelBatch** 将产生错误。

如果当调用 **CancelBatch** 时正在编辑当前记录或添加新记录，那么 ADO 首先会调用 [CancelUpdate](cancelupdate-method-ado.md) 方法取消缓存的所有更改。之后，将取消 **Recordset** 中所有挂起的更改。

在调用 **CancelBatch** 之后，有可能无法确定当前记录，尤其是如果当时正在添加新记录。因此，在调用 **CancelBatch** 之后，最好将当前记录位置设置为 **Recordset** 中的已知位置。例如，调用 [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 方法。

如果由于与基础数据冲突（例如，记录已被其他用户删除）使得取消挂起更新的尝试失败，则提供程序将向 [Errors](errors-collection-ado.md) 集合返回警告，但不会停止程序的执行。只有当请求的所有记录都存在冲突时，才会发生运行时错误。可以使用 [Filter](filter-property-ado.md) 属性 (**adFilterAffectedRecords**) 和 [Status](status-property-ado-recordset.md) 属性查找存在冲突的记录。

