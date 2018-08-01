---
title: YEAR Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251513
localization_priority: Normal
ms.assetid: acc136ef-9946-7c12-a467-9ded732a3549
description: 返回一个整数，表示公历年 datetime 或 expression 中，根据系统当前区域和语言设置由设置的短日期样式设置格式。
ms.openlocfilehash: aaa183730440857d8d283912f4afeb3117ef737f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781715"
---
# <a name="year-function-visioshapesheet"></a>YEAR Function (VisioShapeSheet)

返回一个整数，表示公历年_datetime_或_expression_，根据系统当前区域和语言设置由设置的短日期样式设置格式。
  
## <a name="syntax"></a>语法

年 ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**字符串** <br/> | 任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**因情况而异** <br/> |任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Numeric** <br/> |用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

Integer
  
## <a name="remarks"></a>说明

_Datetime_或_expression_中的时间组件已被丢弃。 
  
无舍入过程。 如果_datetime_缺失或无法解释为有效的日期或时间，年将返回错误。 
  
YEAR 函数还接受值为单一数值的_表达式_，其中结果的整数部分代表自 1899 年 12 月 30 日以来的天数。 
  
## <a name="example-1"></a>示例 1

YEAR("10/27/2007 13:45:24")
  
返回 2007。
  
## <a name="example-2"></a>示例 2

YEAR(DATEVALUE("Dec. 25, 2006") + 7 ed.)
  
返回 2007。
  
## <a name="example-3"></a>示例 3

YEAR(35580.6337)
  
返回 1997。
  

