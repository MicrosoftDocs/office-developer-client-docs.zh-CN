---
title: 关于日期、时间和持续时间值
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251852
localization_priority: Normal
ms.assetid: b6951a92-f32a-5829-5e07-b277b7934df3
description: 您可以在公式中使用日期、时间和持续时间值执行运算。在 Microsoft Visio 中，日期和时间表达式可以计算为单个值。日期和时间表达式是任何公认的日期和/或时间表达式，或者是对包含日期和/或时间的单元格的引用。这里所指的日期和/或时间包括显示为日期和时间的字符串和数字，以及从函数返回的日期和时间值。
ms.openlocfilehash: 936055ed6d13b75bd0c42c95564046a76082ec0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779613"
---
# <a name="about-date-time-and-duration-values"></a>关于日期、时间和持续时间值

您可以在公式中使用日期、时间和持续时间值执行运算。在 Microsoft Visio 中，日期和时间表达式可以计算为单个值。日期和时间表达式是任何公认的日期和/或时间表达式，或者是对包含日期和/或时间的单元格的引用。这里所指的日期和/或时间包括显示为日期和时间的字符串和数字，以及从函数返回的日期和时间值。
  
日期和时间值在 Visio 中以 64 位浮点数在内部存储。小数点左侧的值表示从 1899 年 12 月 30 日至今的天数。小数点右侧的值表示从午夜到现在按分数表示的当日时间，正午用 .5 表示。
  
要在表达式中使用多个日期和时间（而不是作为单个常数），必须用相应的函数将它们标识为日期和时间值。
  
## <a name="valid-dates"></a>有效日期

||||
|:-----|:-----|:-----|
| "2/28"  <br/> | "28/2/99"  <br/> | "28/2/1999"  <br/> |
| "2-28"  <br/> | "2-28-99"  <br/> | "1999 年 2-28"  <br/> |
| "6 Mar 99"  <br/> | "6 Mar"  <br/> | "6 Mar 99"  <br/> |
| "1 January 99"  <br/> | "Jan 1, 99"  <br/> | "Jan 1, 1999"  <br/> |
| "Jan 00"  <br/> | "January, 2000"  <br/> | "Jan 1, 00"  <br/> |
   
## <a name="valid-times"></a>有效时间

||||
|:-----|:-----|:-----|
| "3:45"  <br/> | "3: 45:27"  <br/> | "7a"  <br/> |
| "7 am"  <br/> | "7 p"  <br/> | "7:30 PM"  <br/> |
   
## <a name="date-and-time-functions"></a>日期和时间函数

|**函数**|**说明**|
|:-----|:-----|
|[日期](date-function-visioshapesheet.md) <br/> | 将数字转换为日期值。  <br/> |
|[DATETIME](datetime-function.md) <br/> | 将字符串转换为日期和时间值。  <br/> |
|[DATEVALUE](datevalue-function-visioshapesheet.md) <br/> | 将字符串转换为日期值。  <br/> |
|[立即](now-function-visioshapesheet.md) <br/> | 以日期和时间值返回当前系统日期。  <br/> |
|[时间](time-function-visioshapesheet.md) <br/> | 将数字转换为时间值。  <br/> |
|[TIMEVALUE](timevalue-function-visioshapesheet.md) <br/> | 将字符串转换为时间值。  <br/> |
|[一天](day-function-visioshapesheet.md) <br/> | 返回日期和时间表达式中的日期部分。  <br/> |
|[DAYOFYEAR](dayofyear-function.md) <br/> | 根据日期和时间表达式，返回从年初至今的天数。  <br/> |
|[小时](hour-function-visioshapesheet.md) <br/> | 返回日期和时间表达式中的小时部分。  <br/> |
|[分钟](minute-function-visioshapesheet.md) <br/> | 返回日期和时间表达式中的分钟部分。  <br/> |
|[月](month-function-visioshapesheet.md) <br/> | 返回日期和时间表达式中的月部分。  <br/> |
|[第二个](second-function-visioshapesheet.md) <br/> | 返回日期和时间表达式中的秒部分。  <br/> |
|[WEEKDAY](weekday-function-visioshapesheet.md) <br/> | 返回日期和时间表达式中一个星期中的第几天。  <br/> |
|[年](year-function-visioshapesheet.md) <br/> | 返回日期和时间表达式中的年部分。  <br/> |
   
## <a name="duration"></a>Duration

您可以执行用来计算持续时间或经过时间的运算。持续时间在内部存储为整天数和分数天数。例如，经过 1 周、经过 7 日以及经过 168 个小时都在内部存储为 7.0，但它们会以适当的单位显示。
  
Visio 可识别下表中的持续时间单位。
  
|**Unit**|**Abbreviation**|**通用缩写形式**|
|:-----|:-----|:-----|
| 已用天数  <br/> | eday、ed.  <br/> | ed  <br/> |
| 已用小时数  <br/> | ehour、eh.  <br/> | eh  <br/> |
| 已用分钟数  <br/> | eminute、em.  <br/> | em  <br/> |
| 已用秒数  <br/> | esecond、es.  <br/> | es  <br/> |
| 已用星期数  <br/> | eweek、ew.  <br/> | ew  <br/> |
   
您可以将日期和时间与持续时间相加得到一个新的日期和时间。还可以用日期、时间和持续时间执行在下表中列出的运算。
  
|**输入**|**结果**|
|:-----|:-----|
| 日期时间 +/- 持续时间  <br/> | 日期和时间值  <br/> |
| 持续时间 +/- 日期时间  <br/> | 日期和时间值  <br/> |
| 持续时间 +/- 持续时间  <br/> | 持续时间值  <br/> |
| 日期时间 + 日期时间  <br/> | 日期和时间值  <br/> |
| 日期时间 - 日期时间  <br/> | 持续时间值  <br/> |
   

