---
title: WEEKDAY Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251512
localization_priority: Normal
ms.assetid: f2625ef8-3bdb-5a8d-48b9-149be0592533
description: 返回一个表示整数，1 到 7 datetime 或 expression 中的工作日。
ms.openlocfilehash: decc89c93d175b357cdfe2b8377d04517b92ccab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781658"
---
# <a name="weekday-function-visioshapesheet"></a>WEEKDAY Function (VisioShapeSheet)

返回一个表示整数，1 到 7 _datetime_或_expression_中的工作日。
  
## <a name="syntax"></a>语法

WEEKDAY ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**字符串** <br/> | 任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**因情况而异** <br/> |任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Numeric** <br/> |用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

Integer
  
## <a name="remarks"></a>说明

_Datetime_或_expression_中的时间组件已被丢弃。 
  
结果对应于星期一 (1) 到星期日 (7)。 无舍入过程。 如果_datetime_缺失或无法解释为有效的日期或时间，则函数返回 #VALUE ！ 错误。 
  
WEEKDAY 函数还接受值为单一数值的_表达式_，其中结果的整数部分代表自 1899 年 12 月 30 日以来的天数。 
  
## <a name="example-1"></a>示例 1

WEEKDAY("May 30, 1999")
  
返回 7。
  
## <a name="example-2"></a>示例 2

WEEKDAY(DATEVALUE("May 30, 1999")+2 ed.)
  
返回 2。
  
## <a name="example-3"></a>示例 3

WEEKDAY(35880.6337)
  
返回 4。
  

