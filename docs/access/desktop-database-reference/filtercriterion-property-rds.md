---
title: FilterCriterion 属性 (RDS)
TOCTitle: FilterCriterion property (RDS)
ms:assetid: 51e6cb64-a404-114e-8e1a-0744cceeec3e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249267(v=office.15)
ms:contentKeyID: 48544834
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 65541e8f64c5a019679252246edbe8027130c4ed
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292424"
---
# <a name="filtercriterion-property-rds"></a>FilterCriterion 属性 (RDS)

**适用于**：Access 2013、Office 2013

指示筛选值中使用的求值运算符。

## <a name="syntax"></a>语法

*rds.datacontrol*。FilterCriterion = *String*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*DataControl* |一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|
|*String* |一个 **String** 值，指定记录的 [FilterValue](filtervalue-property-rds.md) 的求值运算符。 可以\<是下列任一项:、 \<=、 \>、 \>=、= 或。 \< \>|

## <a name="remarks"></a>注解

[SortColumn](sortcolumn-property-rds.md)、[SortDirection](sortdirection-property-rds.md)、[FilterValue](filtervalue-property-rds.md)、**FilterCriterion** 和 [FilterColumn](filtercolumn-property-rds.md) 属性提供客户端缓存的排序和筛选功能。排序功能根据某一列的值对记录进行排序。筛选功能根据查找条件显示记录的子集，而整个 [Recordset](recordset-object-ado.md) 则保留在缓存中。[Reset](reset-method-rds.md) 方法将执行条件，并用可更新的 **Recordset** 替换当前的 **Recordset**。

"\!=" 运算符对**FilterCriterion**无效;相反, 请使用\<\>""。

如果同时设置了筛选和排序属性并调用 **Reset** 方法，将首先筛选行集，然后再对其进行排序。对于升序排列，Null 值位于顶部；对于降序排列，Null 值位于底部（默认行为是升序）。

