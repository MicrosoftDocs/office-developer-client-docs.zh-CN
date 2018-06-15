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
description: 计算文本块的正确的要防止颠倒文本的指定的形状旋转的旋转角度。
ms.openlocfilehash: 0d8b0160c7e7d63fb5a272219a2694d35e6e6b61
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19780356"
---
# <a name="gravity-function"></a>GRAVITY 函数

计算文本块的正确的要防止颠倒文本的指定的形状旋转的旋转角度。
  
## <a name="syntax"></a>语法

GRAVITY (* **角度** *，[* **介于 limit1* * *]，[* * *limit2* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _角度_ <br/> |必需  <br/> |**字符串** <br/> | 形状的角度。  <br/> |
| _介于 limit1_ <br/> |可选  <br/> |**字符串** <br/> |第一个旋转限制条件。默认值为 90 度。  <br/> |
| _limit2_ <br/> |可选  <br/> |**字符串** <br/> |第二个旋转限制条件。默认值为 270 度。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>注解

GRAVITY 函数通常在 TxtAngle 单元格中使用。 
  
如果_angle_ _介于 limit1_和_limit2_; 指定的值之间，则，返回的值是 180 度否则，返回的值是 0 度。
  
所有参数都由该函数在 0 和 360 度之间自动规范化。如果参数未指定单位，则假定为弧度。 
  
## <a name="example-1"></a>示例 1

GRAVITY(Angle)
  
返回 180 度如果*angle*介于 90 至 270 度;否则，返回 0 度。 
  
## <a name="example-2"></a>示例 2

GRAVITY(2)
  
返回 180 度，因为 2 弧度介于 90 至 270 度之间。
  
## <a name="example-3"></a>示例 3

GRAVITY(100 deg, 110 deg, 290 deg)
  
返回 0 度。
  
## <a name="example-4"></a>示例 4

GRAVITY(100 deg, 290 deg, 110 deg)
  
返回 0 度。
  

