---
title: TIMEVALUE 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251507
localization_priority: Normal
ms.assetid: 53579e0e-fcec-e745-0207-3861b5efa333
description: 基于系统的区域和语言设置, 返回由 datetime 或 expression 表示的时间值。
ms.openlocfilehash: 61eeafac64ce199eba0f9032c42474d2b44febce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361108"
---
# <a name="timevalue-function-visioshapesheet"></a>TIMEVALUE 函数 (VisioShapeSheet)

基于系统的区域和语言设置, 返回由_datetime_或_expression_表示的时间值。
  
## <a name="syntax"></a>语法

TIMEVALUE ("* * *datetime* * *" |* **表达式** * [, * * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**String** <br/> | 任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**相同** <br/> | 任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Number** <br/> |用于计算非本地日期时间的区域设置标识符。 区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
## <a name="remarks"></a>注解

_datetime_或_expression_中的任何日期部分都将被丢弃。 
  
如果_datetime_缺失或无法转换为有效的结果, 则此函数返回一个 #VALUE! 误差. 
  
TIMEVALUE 函数还接受一个数值, 其中结果的__ 小数部分表示自午夜以来的一天中的某一天。 
  
## <a name="example-1"></a>示例 1

TIMEVALUE("6:00 AM")
  
返回表示上午 6:00 的值。
  
## <a name="example-2"></a>示例 2

TIMEVALUE("14:30")+4 eh.+30 em.
  
返回表示下午 7:00:00 的值。
  
## <a name="example-3"></a>示例 3

TIMEVALUE("11 AM, July 1, 1997")
  
返回表示上午 11:00 的值。
  
## <a name="example-4"></a>示例 4

TIMEVALUE (0.6337)
  
返回表示下午 3:12:32 的值。
  
## <a name="example-5"></a>示例 5

TIMEVALUE ("7:89")
  
返回 #VALUE! 错误。
  

