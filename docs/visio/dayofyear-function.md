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
description: 返回一个介于1到366之间的整数, 该整数表示日期时间或表达式中的一年中的连续日期。 DAYOFYEAR 函数使用公历日历。
ms.openlocfilehash: 30c0331a57282baee97e81689b6a8f362581b8f1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360290"
---
# <a name="dayofyear-function"></a>DAYOFYEAR 函数

返回一个介于1到366之间的整数, 该整数表示_日期时间_或_表达式_中的一年中的连续日期。 DAYOFYEAR 函数使用公历日历。
  
## <a name="syntax"></a>语法

DAYOFYEAR ("* * *datetime* * *" |* **表达式** * [, * * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**String** <br/> |任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**String** <br/> |任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Number** <br/> |指定用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

整数
  
## <a name="remarks"></a>注解

_datetime_或_expression_中的任何时间组件都将被丢弃。 
  
结果对应 1 月 1 日至 12 月 31 日。 无舍入过程。 如果_datetime_缺失或无法解释为有效的日期或时间, 则函数将返回错误。 
  
DAYOFYEAR 函数还接受单个数值_表达式_, 其中结果的整数部分代表自1899年12月30日的天数。 
  
## <a name="example-1"></a>示例 1

DAYOFYEAR("May 30, 1997 13:45:24")
  
返回 150。
  
## <a name="example-2"></a>示例 2

DAYOFYEAR(DATEVALUE("May 30, 1997")+7 ed.)
  
返回 157。
  
## <a name="example-3"></a>示例 3

DAYOFYEAR (35580.6337)
  
返回 150。
  

