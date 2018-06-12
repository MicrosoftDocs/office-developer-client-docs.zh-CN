---
title: HOUR 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251437
localization_priority: Normal
ms.assetid: 2a21d6f9-bad6-92ab-6d36-477bcb9d7f17
description: 返回一个表示整数，0 到 23 datetime 或 expression 的一天的。
ms.openlocfilehash: 9cfe8c88a4a4d73be23b2ac230b0cfabc955c004
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780408"
---
# <a name="hour-function-visioshapesheet"></a>HOUR 函数 (VisioShapeSheet)

返回一个表示整数，0 到 23 _datetime_或_expression_的一天的。
  
## <a name="syntax"></a>语法

小时 ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**字符串** <br/> | 通常被识别为表示日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**而异** <br/> |生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**编号** <br/> | 用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
## <a name="remarks"></a>注解

*Datetime*和*expression*中的日期部分将被丢弃。 
  
无舍入过程。 如果*datetime*缺失或无法转换为有效的结果，则函数将返回错误。 
  
返回的值根据系统当前“区域设置”中设置的时间样式设置格式。 
  
HOUR 函数还接受值为单一数值的*表达式*，其中结果的小数部分代表自午夜开始的一天的时间占。 
  
## <a name="example-1"></a>示例 1

HOUR("15:45")
  
返回 15。
  
## <a name="example-2"></a>示例 2

HOUR("May 30, 1997 3:45:24 PM")
  
返回 15。
  
## <a name="example-3"></a>示例 3

HOUR(0.5)
  
返回 12。
  
## <a name="example-4"></a>示例 4

HOUR("5/30/1997")
  
返回 0。
  

