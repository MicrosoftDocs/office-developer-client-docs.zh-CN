---
title: NURBS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251579
localization_priority: Normal
ms.assetid: f34db20d-6501-2026-a5e8-29c4d4cb2405
description: 返回一个非均匀有理 B 样条 (NURBS)。 此函数用于 NURBSTo 几何图形行中的 E 单元格。
ms.openlocfilehash: af92374a829c0df8e71ac81e630abc4fa64988dc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340122"
---
# <a name="nurbs-function"></a>NURBS 函数

返回一个非均匀有理 B 样条 (NURBS)。 此函数用于 NURBSTo 几何图形行中的 E 单元格。
  
## <a name="syntax"></a>语法

NURBS (* * *knotLast* * *、* **度** *、* * *xType* * *、* * *yType* * *、* * *x1* * *、* * *y1* * *、* * *knot1* * *、* * *weight1* * *、* * * *、* * * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _knotLast_ <br/> |必需  <br/> |**string** <br/> | 最后一个节点。  <br/> |
| _°_ <br/> |必需  <br/> |**Numeric** <br/> |样条的度数。  <br/> |
| _xType_ <br/> |必需  <br/> |**Numeric** <br/> |指定如何解释_x_输入数据。 如果_xType_为 0, 则所有_x_输入数据都被解释为宽度的百分比。 如果_xType_为 1, 则所有_x_输入数据将被解释为本地坐标。  <br/> |
| _yType_ <br/> |必需  <br/> |**Numeric** <br/> |指定如何解释_y_输入数据。 如果_yType_为 0, 则所有_y_输入数据将被解释为高度的百分比。 如果_yType_为 1, 则所有_y_输入数据将被解释为本地坐标。  <br/> |
| _x1_ <br/> |必需  <br/> |**String** <br/> |x 坐标。  <br/> |
| _y1_ <br/> |必需  <br/> |**String** <br/> |y 坐标。  <br/> |
| _knot1_ <br/> |必需  <br/> |**String** <br/> |B 样条上的节点。  <br/> |
| _weight1_ <br/> |必需  <br/> |**String** <br/> |B 样条的粗细。  <br/> |
   
## <a name="remarks"></a>注解

对于每个*x*参数, 必须有一个*y*参数;否则, 将返回错误。 
  
您必须指定至少一个*x*、 *y*、*节点*和*权重*参数;否则, Visio 将返回错误。 
  

