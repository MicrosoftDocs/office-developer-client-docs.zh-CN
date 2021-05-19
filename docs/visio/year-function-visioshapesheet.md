---
title: YEAR 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251513
localization_priority: Normal
ms.assetid: acc136ef-9946-7c12-a467-9ded732a3549
description: 返回一个整数，该整数表示日期时间或表达式中的公历年，根据系统的当前"地区"和"语言"设置设置的短日期样式进行格式设置。
ms.openlocfilehash: c9bacd34557d365841171bee5c9f4683e6a3d296
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420708"
---
# <a name="year-function-visioshapesheet"></a>YEAR 函数 (VisioShapeSheet)

返回一个整数，该整数表示日期时间或表达式中的公历年，根据系统的当前"地区"和"语言"设置设置的短日期样式设置格式。
  
## <a name="syntax"></a>语法

YEAR (" ** *datetime* ** "|** *expression* ** [， ** *lcid* ** ])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**String** <br/> | 任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**变化** <br/> |任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Numeric** <br/> |用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

整数
  
## <a name="remarks"></a>备注

datetime 或 expression _中__的时间_ 部分将被丢弃。 
  
无舍入过程。 如果  _datetime_ 缺失或无法解释为有效的日期或时间，则 YEAR 将返回错误。 
  
YEAR 函数还接受单个数值的  _expression，_ 其中结果的整数部分表示自 1899 年 12 月 30 日起的天数。 
  
## <a name="example-1"></a>示例 1

YEAR ("10/27/2007 13：45：24") 
  
返回 2007。
  
## <a name="example-2"></a>示例 2

YEAR(DATEVALUE("Dec. 25, 2006") + 7 ed.)
  
返回 2007。
  
## <a name="example-3"></a>示例 3

YEAR (35580.6337) 
  
返回 1997。
  

