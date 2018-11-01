---
title: FilterColumn 属性 (RDS)
TOCTitle: FilterColumn Property (RDS)
ms:assetid: fb5d9f23-b62a-8131-d6ff-8b7ed8bb825c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250287(v=office.15)
ms:contentKeyID: 48548868
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9cf03a2cbff06919981ac940f5b2962062a850c2
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877798"
---
# <a name="filtercolumn-property-rds"></a>FilterColumn 属性 (RDS)


**适用于**： Access 2013、 Office 2013



指示要在其中计算筛选条件的列。

## <a name="syntax"></a>语法

*DataControl*。FilterColumn =*字符串*

## <a name="parameters"></a>参数

  - *DataControl*

  - 一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。

  - *String*

  - 一个 **String** 值，指定要在其上计算筛选条件的列。筛选条件在 [FilterCriterion](filtercriterion-property-rds.md) 属性中指定。

## <a name="remarks"></a>备注

[SortColumn](sortcolumn-property-rds.md)、 [SortDirection](sortdirection-property-rds.md) 、 [FilterValue](filtervalue-property-rds.md)、[FilterCriterion](filtercriterion-property-rds.md) 和 **FilterColumn** 属性提供客户端缓存的排序和筛选功能。排序功能根据某一列的值对记录进行排序。筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。 [Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。

