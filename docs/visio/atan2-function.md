---
title: ATAN2 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251397
localization_priority: Normal
ms.assetid: 524278fb-196e-9cf9-e27b-d03642beeee4
description: 返回由 x、y 和 x 轴方向表示的向量之间的角度。 结果是用当前的角度度量单位表示的数值。
ms.openlocfilehash: 906c024f2a78d6e11c1bbf770c14d04299cadca8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341480"
---
# <a name="atan2-function"></a>ATAN2 函数

返回由*x、y*和*x*轴方向表示的向量之间的角度。 结果是用当前的角度度量单位表示的数值。 
  
## <a name="syntax"></a>语法

ATAN2 (* * *y* * *, * * *x* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _y_ <br/> |必需  <br/> |**Numeric** <br/> |点的_y_值。  <br/> |
| _x_ <br/> |必需  <br/> |**Numeric** <br/> |点的_x_值。  <br/> |
   
## <a name="remarks"></a>注解

反正切值是从正*x*轴到与原点 (0, 0) 和由*x*和*y*表示的点相交的直线的逆时针测量角。 在 Microsoft Visio 中，ATAN2(0,0) 返回 0。 若要将 ATAN2 结果强制为其他角度度量单位，请使用 DEG 或 RAD 函数。 
  
ATAN2 函数是 TAN 函数的 antifunction。 ATAN2 函数返回角度等于*y*除以*x*的角的角度。 如果 ATAN2 (*y, x*) 表示直角三角形中的角度, 则*y*是 "相对边", *x*是 "相邻侧", 因此函数可以编写为 ATAN2 (反向, 相邻)。 
  
## <a name="example-1"></a>示例 1

ATAN2 (1.25, 2.25)
  
返回 29.0456 度
  
## <a name="example-2"></a>示例 2

ATAN2 (1, SQRT (3))
  
返回 30 度
  
## <a name="example-3"></a>示例 3

ATAN2 (1, 1)
  
返回 45 度
  

