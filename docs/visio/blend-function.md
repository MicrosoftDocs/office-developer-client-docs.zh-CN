---
title: BLEND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c67b46bb-0eb2-f094-2870-c320bd488705
description: 混合两种颜色按 float 参数指定的比例。
ms.openlocfilehash: 61993cea9eed6583d62004e1c756368b67c7bb33
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779768"
---
# <a name="blend-function"></a>BLEND 函数

混合两种颜色按_float_参数指定的比例。 
  
## <a name="syntax"></a>语法

混合 (* * *color1* * *，* * *color2* * *，* * *float [0，1]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color1_ <br/> |必需  <br/> |**数字** <br/> |Visio 第一种颜色的颜色索引或 RGB 值。  <br/> |
| _color2_ <br/> |必需  <br/> |**数字** <br/> |Visio 第二种颜色的颜色索引或 RGB 值。  <br/> |
| _float [0，1]_ <br/> |必需  <br/> |**Float** <br/> |用于混合_color2_和_color1_，分别比例。 实数从 0 到 1 之间。  <br/> |
   
### <a name="return-value"></a>返回值

 **RGB**
  
## <a name="remarks"></a>备注

返回的颜色由用于混合_color2_和_color1_，分别，按_float_参数指定的相对比例决定。 例如，如果_float_为 0.25，返回的颜色是 color1 的组合的 75%__ 和_color2_的 25%。 
  
另一种方法需要考虑的事项它是对应于沿颜色彩虹的点的_浮点_值从_color1_到_color2_。 因此，较小数字 （接近零） 的接近_float_生成混合_color1_，对大数字 （接近 1） 时生成混合接近到_color2_。
  

