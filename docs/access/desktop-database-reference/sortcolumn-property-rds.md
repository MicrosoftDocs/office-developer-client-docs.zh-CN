---
title: SortColumn 属性 (RDS)
TOCTitle: SortColumn property (RDS)
ms:assetid: 0a5d157c-9261-960d-6f89-33d9c94b3940
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248835(v=office.15)
ms:contentKeyID: 48543151
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 54e6df1f2a94bd59f1e4cf9f9c0be77d785a3048
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306886"
---
# <a name="sortcolumn-property-rds"></a>SortColumn 属性 (RDS)

**适用于**：Access 2013、Office 2013

指示作为记录的排序依据的列。

## <a name="syntax"></a>语法

*rds.datacontrol*。SortColumn = *String*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*DataControl* |一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|
|*String* |一个 **String** 值，表示作为记录的排序依据的列的名称或别名。|

## <a name="remarks"></a>注解

**SortColumn**、[SortDirection](sortdirection-property-rds.md)、[FilterValue](filtervalue-property-rds.md)、[FilterCriterion](filtercriterion-property-rds.md) 和 [FilterColumn](filtercolumn-property-rds.md) 属性提供客户端缓存的排序和筛选功能。排序功能根据某一列的值对记录进行排序。筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。[Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset**。

若要对 **Recordset** 进行排序，必须首先保存所有挂起的更改。 如果正在使用 **RDS.DataControl**，则可以使用 [SubmitChanges](submitchanges-method-rds.md) 方法。 例如, 如果您的**RDS。rds.datacontrol**命名为 ADC1, 则您的代码将为 ADC1。SubmitChanges. 如果正在使用 ADO **Recordset**，则可以使用其 [UpdateBatch](updatebatch-method-ado.md) 方法。 对于用 [CreateRecordset](createrecordset-method-rds.md) 方法创建的 **Recordset** 对象，建议使用 **UpdateBatch** 方法。 例如, 您的代码可能是 myRS 或。 如果正在使用 ADO **Recordset**，则可以使用其 [UpdateBatch](updatebatch-method-ado.md) 方法。 对于用 [CreateRecordset](createrecordset-method-rds.md) 方法创建的 **Recordset** 对象，建议使用 **UpdateBatch** 方法。 例如, 您的代码可能是 myRS 或 ADC1。Recordset。

