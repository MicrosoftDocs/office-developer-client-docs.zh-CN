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
description: 返回表示的时间值的 datetime 或 expression 中，将根据系统的区域和语言设置。
ms.openlocfilehash: e75607d19dc7062af717823c13f580cb44c9406b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781522"
---
# <a name="timevalue-function-visioshapesheet"></a>TIMEVALUE 函数 (VisioShapeSheet)

_Datetime_或_expression_返回表示的时间值将基于系统的区域和语言设置。
  
## <a name="syntax"></a>语法

TIMEVALUE ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**字符串** <br/> | 任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**而异** <br/> | 任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**编号** <br/> |用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
## <a name="remarks"></a>注解

_Datetime_或_expression_中的任何日期部分将被丢弃。 
  
如果_datetime_缺失或无法转换为有效的结果，则此函数返回 #VALUE ！ 错误。 
  
TIMEVALUE 函数还接受值为单一数值的_表达式_，其中结果的小数部分代表自午夜开始的一天的时间占。 
  
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

TIMEVALUE(0.6337)
  
返回表示下午 3:12:32 的值。
  
## <a name="example-5"></a>示例 5

TIMEVALUE("7:89")
  
返回 #VALUE! 错误。
  

