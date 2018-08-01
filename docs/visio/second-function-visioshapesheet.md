---
title: SECOND Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251495
localization_priority: Normal
ms.assetid: 22005976-37c0-d2be-8e34-8aee8458e4be
description: 返回一个整数，介于 0 和 59，值，该值代表 datetime 或 expression 的秒部分。
ms.openlocfilehash: 5f0a3e87763bd4ea5436afe221e12477e9186356
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781223"
---
# <a name="second-function-visioshapesheet"></a>SECOND Function (VisioShapeSheet)

返回一个整数，介于 0 和 59，值，该值代表_datetime_或_expression_的秒部分。
  
## <a name="syntax"></a>语法

第二个 ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**字符串** <br/> |任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**字符串** <br/> | 任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Numeric** <br/> |用于评估非本地_datetime_的区域设置标识符。 区域设置标识符是系统头文件中所述的数字。  <br/> |
   
### <a name="return-value"></a>返回值

Integer
  
## <a name="remarks"></a>说明

_Datetime_或_expression_中的日期部分将被丢弃。 
  
无舍入过程。 如果_datetime_缺失或无法转换为有效的结果，此函数将返回错误。 
  
SECOND 函数还接受值为单一数值的_表达式_，其中结果的小数部分代表自午夜开始的一天的时间占。 
  
## <a name="example-1"></a>示例 1

SECOND("05/30/1997 13:45:32")
  
返回 32。
  
## <a name="example-2"></a>示例 2

SECOND(TIMEVALUE("May 30, 1996 12:07:45") + 7 es.)
  
返回 52。
  
## <a name="example-3"></a>示例 3

SECOND(0.6337)
  
返回 32。
  

