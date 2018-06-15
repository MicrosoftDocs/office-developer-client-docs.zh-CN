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
description: 返回非均匀有理 B 样条 (NURBS)。 NURBSTo geometry 行中的 E 单元格中使用此函数。
ms.openlocfilehash: 005a66b9da2425beaf416ec2273c10446c183add
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19780834"
---
# <a name="nurbs-function"></a>NURBS 函数

返回非均匀有理 B 样条 (NURBS)。 NURBSTo geometry 行中的 E 单元格中使用此函数。
  
## <a name="syntax"></a>语法

NURBS (* * *knotLast* * *，* **度** *，* * *xType* * *，* * *yType* * *，* * *x1* * *，* * *y1* * *，* * *knot1* * *，* * *weight1* * *，...) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _knotLast_ <br/> |必需  <br/> |**string** <br/> | 最后一个节点。  <br/> |
| _度_ <br/> |必需  <br/> |**数字** <br/> |样条的度数。  <br/> |
| _xType_ <br/> |必需  <br/> |**数字** <br/> |指定如何解释_x_输入的数据。 如果_xType_为 0，所有_x_输入的数据被都解释为宽度的百分比。 如果_xType_为 1 时，所有_x_输入的数据被都解释为本地坐标。  <br/> |
| _yType_ <br/> |必需  <br/> |**数字** <br/> |指定如何解释_y_输入的数据。 如果_yType_为 0，所有_y_输入的数据被都解释为高度的百分比。 如果_yType_为 1 时，所有_y_输入的数据被都解释为本地坐标。  <br/> |
| _x1_ <br/> |必需  <br/> |**字符串** <br/> |x 坐标。  <br/> |
| _y1_ <br/> |必需  <br/> |**字符串** <br/> |y 坐标。  <br/> |
| _knot1_ <br/> |必需  <br/> |**字符串** <br/> |B 样条上的节点。  <br/> |
| _weight1_ <br/> |必需  <br/> |**字符串** <br/> |B 样条的粗细。  <br/> |
   
## <a name="remarks"></a>注解

对于每一个*x*参数，必须有一个*y*参数;否则，将返回错误。 
  
必须指定至少一个*x*、 *y*、*节点*和*weight*参数;否则，Visio 将返回错误。 
  

