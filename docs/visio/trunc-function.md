---
title: TRUNC 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251508
localization_priority: Normal
ms.assetid: 62f074ef-5bf8-df1e-d826-fc1027a36501
description: 返回一个截断为指定的数字位数的数字。
ms.openlocfilehash: 8f6a9798391d308a234469d93bc8f481de5fc8da
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781557"
---
# <a name="trunc-function"></a>TRUNC 函数

返回一个截断为指定的数字位数的数字。
  
## <a name="syntax"></a>语法

TRUNC (* **数量** *，* * *numberofdigits* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**数字** <br/> |要截断的数字。  <br/> |
| _numberofdigits_ <br/> |必需  <br/> |**数字** <br/> |要_截断_的数字数。  <br/> |
   
### <a name="return-value"></a>返回值

Numeric。
  
## <a name="remarks"></a>注解

如果_numberofdigits_大于 0，_数字_将被截断到小数点右边的_numberofdigits_ 。 如果_numberofdigits_为 0，_数字_将被截断为一个整数值。 如果_numberofdigits_小于 0，_数字_将被截断到_numberofdigits_小数点左侧。 
  
## <a name="example-1"></a>示例 1

TRUNC(123.654,2)
  
返回 123.65。
  
## <a name="example-2"></a>示例 2

TRUNC(123.654,0)
  
返回 123。
  
## <a name="example-3"></a>示例 3

TRUNC(123.654,-1)
  
返回 120。
  

