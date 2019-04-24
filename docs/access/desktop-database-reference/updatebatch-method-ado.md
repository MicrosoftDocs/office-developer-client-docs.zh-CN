---
title: UpdateBatch 方法 (ADO)
TOCTitle: UpdateBatch method (ADO)
ms:assetid: 69e72a65-b637-36fd-d09f-7f81050f71ad
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249416(v=office.15)
ms:contentKeyID: 48545420
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9d269a9012588a7b82505ac2e28466151715cbb0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32313574"
---
# <a name="updatebatch-method-ado"></a>UpdateBatch 方法 (ADO)

**适用于**：Access 2013、Office 2013

用于将所有挂起的批更新写入磁盘。

## <a name="syntax"></a>语法

*recordset*。UpdateBatch*AffectRecords*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*AffectRecords* |可选。[AffectEnum](affectenum.md) 值，指示 **UpdateBatch** 方法将影响的记录数。|

## <a name="remarks"></a>注解

以批更新模式修改 **Recordset** 对象时，可以使用 **UpdateBatch** 方法将在 **Recordset** 对象中所做的所有更改传输到基础数据库中。

如果 **Recordset** 对象支持批更新，则在调用 **UpdateBatch** 方法前，可以将对一个或多个记录所做的多次更改缓存在本地。如果在调用 **UpdateBatch** 方法时正在编辑当前记录或添加新记录，则在将批更改传输到提供程序前，ADO 将自动调用 [Update](update-method-ado.md) 方法来保存对当前记录所做的所有挂起的更改。批更新只应与键集或静态游标一起使用。

> [!NOTE]
> 如果当前 **Recordset** 中没有可见记录（如没有满足筛选器的记录），则指定 **adAffectGroup** 作为此参数的值将导致出错。

如果由于与基础数据冲突（例如，记录已被其他用户删除）使得传输任意记录或所有记录的更改的尝试失败，则提供程序将向 [Errors](errors-collection-ado.md) 集合返回警告，并会发生运行时错误。可以使用 [Filter](filter-property-ado.md) 属性 (**adFilterAffectedRecords**) 和 [Status](status-property-ado-recordset.md) 属性查找存在冲突的记录。

若要取消挂起的所有批更新，请使用 [CancelBatch](cancelbatch-method-ado.md) 方法。

如果设置了 [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 和 [Update Resync](update-resync-property-dynamic-ado.md) 动态属性，且 **Recordset** 是对多个表执行 JOIN 操作的结果，那么根据 **Update Resync** 属性的设置，在执行 [UpdateBatch](resync-method-ado.md) 方法后会隐式执行 **Resync** 方法。

对数据源执行各个批更新的次序不一定要与对本地 **Recordset** 执行批更新的次序相同。更新次序取决于提供程序。在编写彼此相关的更新（如针对插入或更新的外键约束）的代码时，应将这一点考虑在内。

