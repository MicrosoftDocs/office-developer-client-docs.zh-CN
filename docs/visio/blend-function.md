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

按 float 参数指定的比例  _混合两种颜色_ 。 
  
## <a name="syntax"></a>语法

BLEND (** *color1* **， ** *color2* **， ** *float[0，1]* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color1_ <br/> |必需  <br/> |**Numeric** <br/> |Visio 第一种颜色的颜色索引或 RGB 值。  <br/> |
| _color2_ <br/> |必需  <br/> |**Numeric** <br/> |Visio 第二种颜色的颜色索引或 RGB 值。  <br/> |
| _float[0，1]_ <br/> |必需  <br/> |**Float** <br/> |分别混合  _color2_ 和  _color1_ 的比例。 0 到 1 之间的实数（包括这两个值）。  <br/> |
   
### <a name="return-value"></a>返回值

 **RGB**
  
## <a name="remarks"></a>备注

返回的颜色由分别混合  _color2_ 和  _color1_ 的相对比例决定，由  _float_ 参数指定。 例如，如果  _float_ 为 0.25，则返回的颜色由  _color1_ 的 75% 和  _color2_ 的 25% 组成。 
  
考虑它的另一种方式是浮点值对应于从 color1 到 _color2_ 的色谱 _中的点_。 因此，浮 (的) 较小的数字会生成更靠近 color1 的混合，而较大的数字 (接近 1) 产生更接近 _color2_ 的 _混合_。
  

