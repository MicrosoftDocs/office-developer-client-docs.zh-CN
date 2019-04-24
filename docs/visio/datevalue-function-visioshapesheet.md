---
title: DATEVALUE 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251414
localization_priority: Normal
ms.assetid: 514a4053-7729-ec82-c42f-5b780e48cd2a
description: 返回以 datetime 或 expression 表示的日期值。
ms.openlocfilehash: d5bc1865e76940508ddb67a9b3d2122dc7c43a50
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360310"
---
# <a name="datevalue-function-visioshapesheet"></a>DATEVALUE 函数 (VisioShapeSheet)

返回以_datetime_或_expression_表示的日期值。
  
## <a name="syntax"></a>语法

DATEVALUE ("* * *datetime* * *" |* **表达式** * [, * * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**String** <br/> |任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**String** <br/> |任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Number** <br/> |指定用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

Datetime
  
## <a name="remarks"></a>注解

*datetime*或*expression*中的任何时间组件都将被丢弃。 
  
如果*datetime*缺失或无法转换为有效的结果, 则 DATEVALUE 将返回 #VALUE! 误差. 
  
返回的值使用由系统当前“区域设置”所设置的短日期样式显示。 
  
DATEVALUE 函数还接受一个数值, 其中结果的** 整数部分代表自1899年12月30日以来的天数。 
  
## <a name="example-1"></a>示例 1

DATEVALUE(NOW( ))+5 ed.
  
返回从现在起五天后的日期。
  
## <a name="example-2"></a>示例 2

DATEVALUE ("7/19/1995 12:30")
  
返回该日期。
  
## <a name="example-3"></a>示例 3

DATEVALUE("May 33, 1997")
  
返回 #VALUE! 错误。
  
## <a name="example-4"></a>示例 4

DATEVALUE (35580.6337)
  
返回 5/30/1997。
  

