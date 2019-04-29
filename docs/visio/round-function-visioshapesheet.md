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
description: 将数字舍入到由 numberofdigits 表示的精度。
ms.openlocfilehash: 6795cbc4d99e293da06c0ec369d2cefb84f9f5b5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439966"
---
# <a name="round-function-visioshapesheet"></a>ROUND 函数 (VisioShapeSheet)

将数字舍入到由*numberofdigits*表示的精度。 
  
## <a name="syntax"></a>语法

ROUND (* * *number* * *, * * *numberofdigits* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Number** <br/> |要舍入的数。  <br/> |
| _numberofdigits_ <br/> |必需  <br/> |**Number** <br/> |精度的小数位数。  <br/> |
   
## <a name="remarks"></a>说明

如果_numberofdigits_大于 0, 则数字将由_numberofdigits_的小数点右边的_数字_舍入。 如果_numberofdigits_为 0, 则将_number_舍入为整数。 如果_numberofdigits_小于 0, 则_数字_将由_numberofdigits_ (小数的左侧) 舍入。 
  
## <a name="example-1"></a>示例 1

ROUND (123.654, 2)
  
返回 123.65。
  
## <a name="example-2"></a>示例 2

ROUND (123.654, 0)
  
返回 124。
  
## <a name="example-3"></a>示例 3

ROUND (123.654,-1)
  
返回 120。
  

