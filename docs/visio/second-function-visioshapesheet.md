---
title: SECOND 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251495
localization_priority: Normal
ms.assetid: 22005976-37c0-d2be-8e34-8aee8458e4be
description: 返回一个整数, 0 到 59, 表示日期时间或表达式的秒部分。
ms.openlocfilehash: c23bbded12a3886fe3bd4dd2a3c3ba1bd6d11619
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332786"
---
# <a name="second-function-visioshapesheet"></a>SECOND 函数 (VisioShapeSheet)

返回一个整数, 0 到 59, 表示_日期时间_或_表达式_的秒部分。
  
## <a name="syntax"></a>语法

SECOND ("* * *datetime* * *" |* **表达式** * [, * * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**String** <br/> |任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**String** <br/> | 任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Numeric** <br/> |用于计算非本地_datetime_的区域设置标识符。 区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

整数
  
## <a name="remarks"></a>注解

_datetime_或_expression_中的日期部分将被丢弃。 
  
无舍入过程。 如果_datetime_缺失或无法转换为有效的结果, 则此函数将返回错误。 
  
第二个函数还接受一个数值, 其中__ 结果的小数部分表示自午夜以来的一天中的某一天。 
  
## <a name="example-1"></a>示例 1

第二个 ("05/30/1997 13:45:32")
  
返回 32。
  
## <a name="example-2"></a>示例 2

SECOND(TIMEVALUE("May 30, 1996 12:07:45") + 7 es.)
  
返回 52。
  
## <a name="example-3"></a>示例 3

SECOND (0.6337)
  
返回 32。
  

