---
title: Reset 方法 (RDS-访问桌面数据库引用)
TOCTitle: Reset Method (RDS)
ms:assetid: 169ebd1e-6071-613e-c065-3af060167456
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248924(v=office.15)
ms:contentKeyID: 48543435
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3932eaab38498b8c82256ceb0de49a9c78030cdd
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467263"
---
# <a name="reset-method-rds"></a>Reset 方法 (RDS)


**适用于**： Access 2013 |Office 2013

根据指定的排序和筛选属性，对客户端 **Recordset** 执行排序或筛选。

## <a name="syntax"></a>语法

*DataControl*。重置 （*值*）

## <a name="parameters"></a>参数

  - *DataControl*

  - 一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。

  - *value*

  - 可选。 **Boolean** 值，如果要对当前"已筛选的"行集进行筛选，则此参数为 **True** （默认值）。 **False** 指示对原始行集进行筛选，删除以前的所有筛选选项。

## <a name="remarks"></a>备注

[SortColumn](sortcolumn-property-rds.md)、[SortDirection](sortdirection-property-rds.md)、[FilterValue](filtervalue-property-rds.md)、[FilterCriterion](filtercriterion-property-rds.md) 和 [FilterColumn](filtercolumn-property-rds.md) 属性提供了对客户端缓存进行排序和筛选的功能。排序功能将按照一列中的值对记录进行排序。筛选功能基于查找条件显示记录的子集，而缓存中保留有完整的 [Recordset](recordset-object-ado.md)。 **Reset** 方法将执行查找条件，并用可更新的 **Recordset** 替换当前 **Recordset** 。

如果对原始数据所做的更改尚未提交，则 **Reset** 方法将失败。首先，请使用 [SubmitChanges](submitchanges-method-rds.md) 方法将所有更改保存在读/写 **Recordset** 中，然后使用 **Reset** 方法对记录进行排序或筛选。

如果您想要对您行集执行多个筛选器，则可以使用可选的*布尔型*参数，则用**Reset**方法。 以下示例显示了具体的操作方法：

