---
title: DATETIME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251413
localization_priority: Normal
ms.assetid: 0bf7f757-0b7f-dec1-9709-6612c9ad0d53
description: 返回以 datetime 或 expression 表示的日期和时间值。
ms.openlocfilehash: 2da084f685c044d48495b04f727a877140b51004
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360317"
---
# <a name="datetime-function"></a>DATETIME 函数

返回以_datetime_或_expression_表示的日期和时间值。
  
## <a name="syntax"></a>语法

DATETIME ("* * *datetime* * *" |* **表达式** * [, * * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**String** <br/> |任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**String** <br/> |任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Number** <br/> |指定用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

Datetime
  
## <a name="remarks"></a>注解

如果*datetime*缺失或无法解释为有效的日期或时间, 则 datetime 将返回 #VALUE! 误差. 
  
返回的值根据系统当前“区域设置”中的短日期样式和时间样式设置格式。 
  
DATETIME 函数还接受一个数值, 其中结果的** 整数部分代表自1899年12月30日以来的天数, 小数部分表示自午夜以来的一天中的某一天。 
  
## <a name="example-1"></a>示例 1

DATETIME("May 30, 1997")+5 ed.
  
返回表示 6/4/1997 的值。
  
## <a name="example-2"></a>示例 2

FORMAT(DATETIME("5/20/1997 14:30:45"),"C")
  
返回字符串“Tuesday, May 20, 1997 2:30:45 PM”。
  
## <a name="example-3"></a>示例 3

DATETIME("1:30 PM July 19")
  
返回表示 7/19/2001 1:30:00 PM 的值（假定当前为 2001 年）。
  
## <a name="example-4"></a>示例 4

DATETIME (35580.6337)
  
返回表示 5/30/1997 3:12:32 PM 的值。
  

