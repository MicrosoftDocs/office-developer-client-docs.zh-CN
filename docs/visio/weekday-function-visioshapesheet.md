---
title: WEEKDAY 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251512
localization_priority: Normal
ms.assetid: f2625ef8-3bdb-5a8d-48b9-149be0592533
description: 返回一个整数, 1 到 7, 代表 datetime 或 expression 中的工作日。
ms.openlocfilehash: 7c5d467d8c6ff14b99b64b8b0462d21d0b769998
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285242"
---
# <a name="weekday-function-visioshapesheet"></a>WEEKDAY 函数 (VisioShapeSheet)

返回一个整数, 1 到 7, 代表_datetime_或_expression_中的工作日。
  
## <a name="syntax"></a>语法

工作日 ("* * *datetime* * *" |* **表达式** * [, * * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**String** <br/> | 任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**相同** <br/> |任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Numeric** <br/> |用于计算非本地日期时间的区域设置标识符。 区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

整数
  
## <a name="remarks"></a>注解

_datetime_或_expression_中的时间部分将被丢弃。 
  
结果对应于星期一 (1) 到星期日 (7)。 无舍入过程。 如果_datetime_缺失或无法解释为有效的日期或时间, 则该函数将返回 #VALUE! 误差. 
  
WEEKDAY 函数还接受单个数值_表达式_, 其中结果的整数部分代表自1899年12月30日的天数。 
  
## <a name="example-1"></a>示例 1

WEEKDAY("May 30, 1999")
  
返回 7。
  
## <a name="example-2"></a>示例 2

WEEKDAY(DATEVALUE("May 30, 1999")+2 ed.)
  
返回 2。
  
## <a name="example-3"></a>示例 3

工作日 (35880.6337)
  
返回 4。
  

