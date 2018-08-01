---
title: DAYOFYEAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251416
localization_priority: Normal
ms.assetid: 154d76a2-81f5-d8b1-b665-26dbae5da615
description: 返回一个整数，1 到 366，值，该值代表 datetime 或 expression 中的年份的顺序天。 DAYOFYEAR 函数使用公历。
ms.openlocfilehash: 2fd80a2554c268d276deaa524a9d98eebc6a48d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780077"
---
# <a name="dayofyear-function"></a>DAYOFYEAR 函数

返回一个整数，1 到 366，值，该值代表_datetime_或_expression_中的年份的顺序天。 DAYOFYEAR 函数使用公历。
  
## <a name="syntax"></a>语法

DAYOFYEAR ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**字符串** <br/> |任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**字符串** <br/> |任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**编号** <br/> |指定用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

Integer
  
## <a name="remarks"></a>说明

_Datetime_或_expression_中的任何时间组件已被丢弃。 
  
结果对应于 1 月 1 日到年 12 月 31 日。 无舍入过程。 如果_datetime_缺失或无法解释为有效的日期或时间，则函数将返回错误。 
  
DAYOFYEAR 函数还接受值为单一数值的_表达式_，其中结果的整数部分代表自 1899 年 12 月 30 日以来的天数。 
  
## <a name="example-1"></a>示例 1

DAYOFYEAR("May 30, 1997 13:45:24")
  
返回 150。
  
## <a name="example-2"></a>示例 2

DAYOFYEAR(DATEVALUE("May 30, 1997")+7 ed.)
  
返回 157。
  
## <a name="example-3"></a>示例 3

DAYOFYEAR(35580.6337)
  
返回 150。
  

