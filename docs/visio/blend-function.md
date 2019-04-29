---
title: BLEND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c67b46bb-0eb2-f094-2870-c320bd488705
description: 按 float 参数指定的比例混合两种颜色。
ms.openlocfilehash: 0a231954370416be201183026424c79942204e12
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432784"
---
# <a name="blend-function"></a>BLEND 函数

按_float_参数指定的比例混合两种颜色。 
  
## <a name="syntax"></a>语法

BLEND (* * *color1* * *, * * *color2* * *, * * *float [0, 1]* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color1_ <br/> |必需  <br/> |**数值** <br/> |Visio 第一种颜色的颜色索引或 RGB 值。  <br/> |
| _color2_ <br/> |必需  <br/> |**数值** <br/> |Visio 第二种颜色的颜色索引或 RGB 值。  <br/> |
| _float [0, 1]_ <br/> |必需  <br/> |**Float** <br/> |分别混合_color2_和_color1_的比例。 0 到 1 之间的实数（包括这两个值）。  <br/> |
   
### <a name="return-value"></a>返回值

 **RGB**
  
## <a name="remarks"></a>说明

返回的颜色由_float_参数所指定的相对比例, 分别与_color2_和_color1_混合而成。 例如, 如果_float_为 0.25, 则返回的颜色由_color1_的 75% 和 25% 的_color2_组成。 
  
要考虑的另一种方法是, _float_值与色谱从_color1_到_color2_的点相对应。 因此, _float_的较小数字 (更接近零) 会产生更接近_color1_的混合, 而较大的数字 (更接近于 1) 产生的融合更接近于_color2_。
  

