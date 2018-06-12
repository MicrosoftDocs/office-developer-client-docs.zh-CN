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
description: 返回表示由 x 的向量之间的角度 y 和 x 方向-轴。 结果是度量的当前单位角度的数字。
ms.openlocfilehash: dfd62ce628a3a46ff14b3ffc3f07074a39c66e14
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779641"
---
# <a name="atan2-function"></a>ATAN2 函数

返回表示的*x，y*和*x*方向的向量之间的角度-轴。 结果是度量的当前单位角度的数字。 
  
## <a name="syntax"></a>语法

ATAN2 (* * *y* * *，* * *x* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _y_ <br/> |必需  <br/> |**数字** <br/> |_Y_-点的值。  <br/> |
| _x_ <br/> |必需  <br/> |**数字** <br/> |_X_-点的值。  <br/> |
   
## <a name="remarks"></a>备注

反正切值是从误报*x*逆时针开始算起的角度-轴相交原点 (0，0) 和*x*和*y*由表示的点的行。 在 Microsoft Visio ATAN2(0,0) 返回 0。 若要强制 ATAN2 到不同的角度度量的结果，请使用度或 RAD 函数。 
  
ATAN2 函数是 TAN 函数 antifunction。 ATAN2 函数返回其角度等于*y*除以*x*的角度。 如果 ATAN2 （*y，x*） 表示角度直角三角形中的、 *y*是"另一侧"和*x*是"相邻端"，因此无法为 ATAN2(opposite,adjacent) 写入函数。 
  
## <a name="example-1"></a>示例 1

ATAN2(1.25,2.25)
  
返回 29.0456 度
  
## <a name="example-2"></a>示例 2

ATAN2(1,SQRT(3))
  
返回 30 度
  
## <a name="example-3"></a>示例 3

ATAN2(1,1)
  
返回 45 度
  

