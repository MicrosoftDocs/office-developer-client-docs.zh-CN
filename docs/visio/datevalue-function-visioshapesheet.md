---
title: DATEVALUE Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251414
localization_priority: Normal
ms.assetid: 514a4053-7729-ec82-c42f-5b780e48cd2a
description: 返回 datetime 或 expression 所表示的日期值。
ms.openlocfilehash: 7fcfd625b5e4e3da71a1b160c074401b672e0be7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780052"
---
# <a name="datevalue-function-visioshapesheet"></a>DATEVALUE Function (VisioShapeSheet)

返回_datetime_或_expression_所表示的日期值。
  
## <a name="syntax"></a>语法

DATEVALUE ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**字符串** <br/> |任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**字符串** <br/> |任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**编号** <br/> |指定用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

Datetime
  
## <a name="remarks"></a>注解

*Datetime*或*expression*中的任何时间组件已被丢弃。 
  
如果*datetime*缺失或无法转换为有效的结果，则 DATEVALUE 返回 #VALUE ！。 错误。 
  
返回的值使用由系统当前“区域设置”所设置的短日期样式显示。 
  
DATEVALUE 函数还接受值为单一数值的*expression* ，其中结果的整数部分代表自 1899 年 12 月 30 日以来的天数。 
  
## <a name="example-1"></a>示例 1

DATEVALUE(NOW( ))+5 ed.
  
返回从现在起五天后的日期。
  
## <a name="example-2"></a>示例 2

DATEVALUE("7/19/1995 12:30")
  
返回该日期。
  
## <a name="example-3"></a>示例 3

DATEVALUE("May 33, 1997")
  
返回 #VALUE! 错误。
  
## <a name="example-4"></a>示例 4

DATEVALUE(35580.6337)
  
返回 5/30/1997。
  

