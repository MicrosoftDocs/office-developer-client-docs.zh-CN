---
title: MINUTE Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251464
localization_priority: Normal
ms.assetid: 5a90cb16-7eef-8876-8e25-408787b16f58
description: 返回一个整数从 0 到 59 值，该值代表 datetime 或 expression 的分钟部分。
ms.openlocfilehash: 7c35ec15f2cebd95bb09924ca94f20630c862360
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780774"
---
# <a name="minute-function-visioshapesheet"></a>MINUTE Function (VisioShapeSheet)

返回一个整数从 0 到 59 值，该值代表*datetime*或*expression*的分钟组件。 
  
## <a name="syntax"></a>语法

分钟 (" *datetime* "| *表达式* [， *lcid* ]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**字符串** <br/> |任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**字符串** <br/> | 任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**编号** <br/> |用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

Integer
  
## <a name="remarks"></a>说明

_Datetime_和_expression_中的日期部分将被丢弃。 
  
无舍入过程。 如果_datetime_缺失或无法转换为有效的结果，则函数将返回错误。 
  
返回的值根据系统当前“区域设置”中设置的时间样式设置格式。
  
MINUTE 函数还接受值为单一数值的_expression_ ，其中小数部分代表自午夜开始的一天的时间占。 
  
## <a name="example-1"></a>示例 1

MINUTE("7/7/1999 13:45:24")
  
返回 45。
  
## <a name="example-2"></a>示例 2

MINUTE(TIMEVALUE("Jan. 25, 1999 12:07:45")+6 em.)
  
返回 13。
  
## <a name="example-3"></a>示例 3

MINUTE(0.575)
  
返回 48。
  

