---
title: ROUND 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251491
localization_priority: Normal
ms.assetid: a374fe7d-7302-5365-81ab-64f5474d9d5c
description: 舍入到由 numberofdigits 的精度。
ms.openlocfilehash: 2457bdf6b46a2bb44b203497f02cc9b2ff034847
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19781129"
---
# <a name="round-function-visioshapesheet"></a>ROUND 函数 (VisioShapeSheet)

舍入到由*numberofdigits*的精度。 
  
## <a name="syntax"></a>语法

ROUND (* **数量** *，* * *numberofdigits* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**编号** <br/> |要舍入的数。  <br/> |
| _numberofdigits_ <br/> |必需  <br/> |**编号** <br/> |精度的小数位数。  <br/> |
   
## <a name="remarks"></a>注解

如果_numberofdigits_大于 0，则会将_number_舍入的_numberofdigits_小数点右边。 如果_numberofdigits_为 0，则会将_number_舍入为一个整数值。 如果_numberofdigits_小于 0，则会将_number_舍入的_numberofdigits_小数点左侧。 
  
## <a name="example-1"></a>示例 1

ROUND(123.654,2)
  
返回 123.65。
  
## <a name="example-2"></a>示例 2

ROUND(123.654,0)
  
返回 124。
  
## <a name="example-3"></a>示例 3

ROUND(123.654,-1)
  
返回 120。
  

