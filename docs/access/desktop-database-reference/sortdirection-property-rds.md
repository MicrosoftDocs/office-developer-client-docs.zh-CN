---
title: SortDirection 属性 (RDS)
TOCTitle: SortDirection Property (RDS)
ms:assetid: 33de0dce-f371-6a54-d179-0627939f5b14
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249106(v=office.15)
ms:contentKeyID: 48544119
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 256e6a878e9c3f382bcd65b9138df7a440bf118c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468278"
---
# <a name="sortdirection-property-rds"></a>SortDirection 属性 (RDS)


**适用于**： Access 2013 |Office 2013


指示排序顺序是升序还是降序。

## <a name="syntax"></a>语法

*DataControl*。SortDirection =*值*

## <a name="parameters"></a>参数

  - *DataControl*

  - 一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。

  - *Value*

  - 一个 **Boolean** 值，如果设置为 **True** ，则指示升序排序。 **False** 指示降序排序。

## <a name="remarks"></a>备注

[SortColumn](sortcolumn-property-rds.md)、 **SortDirection** 、 [FilterValue](filtervalue-property-rds.md)、[FilterCriterion](filtercriterion-property-rds.md) 和 [FilterColumn](filtercolumn-property-rds.md) 属性提供客户端缓存的排序和筛选功能。排序功能根据某一列的值对记录进行排序。筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。 **Reset** 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset** 。

