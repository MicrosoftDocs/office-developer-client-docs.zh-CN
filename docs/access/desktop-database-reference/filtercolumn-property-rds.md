---
title: FilterColumn 属性 (RDS)
TOCTitle: FilterColumn property (RDS)
ms:assetid: fb5d9f23-b62a-8131-d6ff-8b7ed8bb825c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250287(v=office.15)
ms:contentKeyID: 48548868
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d29c591c88de4b53535c26430bf369cbd3f53284
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292438"
---
# <a name="filtercolumn-property-rds"></a>FilterColumn 属性 (RDS)

**适用于**：Access 2013、Office 2013

指示要在其中计算筛选条件的列。

## <a name="syntax"></a>语法

*rds.datacontrol*。FilterColumn = *String*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*DataControl* |一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|
|*String* |一个 **String** 值，指定要在其上计算筛选条件的列。筛选条件在 [FilterCriterion](filtercriterion-property-rds.md) 属性中指定。|

## <a name="remarks"></a>注解

[SortColumn](sortcolumn-property-rds.md)、[SortDirection](sortdirection-property-rds.md)、 [FilterValue](filtervalue-property-rds.md) 、 [FilterCriterion](filtercriterion-property-rds.md) 和 **FilterColumn** 属性提供客户端缓存的排序和筛选功能。 

排序功能根据某一列的值对记录进行排序。 筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。 

[Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。

