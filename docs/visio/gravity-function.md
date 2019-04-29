---
title: GRAVITY 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251433
localization_priority: Normal
ms.assetid: db80f147-71a0-0b23-bc7e-fe1915dfdd21
description: 为指示的形状旋转计算文本块的正确旋转角度, 以防止文本倒置。
ms.openlocfilehash: 77c944d954292e231f8bacbe3c8a4433aad5d689
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429283"
---
# <a name="gravity-function"></a>GRAVITY 函数

为指示的形状旋转计算文本块的正确旋转角度, 以防止文本倒置。
  
## <a name="syntax"></a>语法

重力 (* * *angle* * *、[* **限制 1* * *]、[* * *limit2* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _angle_ <br/> |必需  <br/> |**String** <br/> | 形状的角度。  <br/> |
| _限制1_ <br/> |可选  <br/> |**字符串** <br/> |第一个旋转限制条件。 默认值为 90 度。  <br/> |
| _limit2_ <br/> |可选  <br/> |**字符串** <br/> |第二个旋转限制条件。 默认值为 270 度。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>说明

GRAVITY 函数通常在 TxtAngle 单元格中使用。 
  
如果_angle_值介于_限制 1_和_limit2_指定的值之间, 则返回的值为180度;否则, 返回的值为0度。
  
所有参数都由该函数在 0 和 360 度之间自动规范化。 如果参数未指定单位，则假定为弧度。 
  
## <a name="example-1"></a>示例 1

重力 (角)
  
如果*angle*介于90和270度之间, 则返回180度;否则, 返回0度。 
  
## <a name="example-2"></a>示例 2

重力 (2)
  
返回 180 度，因为 2 弧度介于 90 至 270 度之间。
  
## <a name="example-3"></a>示例 3

GRAVITY(100 deg, 110 deg, 290 deg)
  
返回 0 度。
  
## <a name="example-4"></a>示例 4

GRAVITY(100 deg, 290 deg, 110 deg)
  
返回 0 度。
  

