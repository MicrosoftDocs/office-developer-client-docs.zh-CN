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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711782"
---
# <a name="filtercolumn-property-rds"></a>FilterColumn 属性 (RDS)

**适用于**： Access 2013、 Office 2013

指示要在其中计算筛选条件的列。

## <a name="syntax"></a>语法

*DataControl*。FilterColumn =*字符串*

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*DataControl* |一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|
|*String* |一个 **String** 值，指定要在其上计算筛选条件的列。筛选条件在 [FilterCriterion](filtercriterion-property-rds.md) 属性中指定。|

## <a name="remarks"></a>备注

[SortColumn](sortcolumn-property-rds.md)、[SortDirection](sortdirection-property-rds.md)、[FilterValue](filtervalue-property-rds.md)、[FilterCriterion](filtercriterion-property-rds.md) 和 **FilterColumn** 属性提供了对客户端缓存进行排序和筛选的功能。 

排序功能根据某一列的值对记录进行排序。 筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。 

[Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。

