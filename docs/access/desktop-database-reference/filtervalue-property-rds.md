---
title: FilterValue 属性 (RDS)
TOCTitle: FilterValue property (RDS)
ms:assetid: 66dc14cd-cc14-78cb-cb05-91eefb17ea47
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249399(v=office.15)
ms:contentKeyID: 48545350
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0de54097c7992583851bbbd7b04c40f10fbca76e
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949479"
---
# <a name="filtervalue-property-rds"></a>FilterValue 属性 (RDS)

**适用于**： Access 2013、 Office 2013

指示用于筛选记录的值。

## <a name="syntax"></a>语法

*DataControl*。FilterValue =*字符串*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*DataControl* |一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|
|*String* |一个**字符串**值，该值代表数据值用于筛选记录 （例如，'Programmer' 或 125）。|

## <a name="remarks"></a>备注

[SortColumn](sortcolumn-property-rds.md)、[SortDirection](sortdirection-property-rds.md)、**FilterValue**、[FilterCriterion](filtercriterion-property-rds.md) 和 [FilterColumn](filtercolumn-property-rds.md) 属性提供了对客户端缓存进行排序和筛选的功能。 

排序功能根据某一列的值对记录进行排序。 筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。 [Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。

空值将导致出现类型不匹配错误。

