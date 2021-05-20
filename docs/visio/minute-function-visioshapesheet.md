---
title: MINUTE 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251464
localization_priority: Normal
ms.assetid: 5a90cb16-7eef-8876-8e25-408787b16f58
description: 返回一个 0 到 59 的整数，该整数表示 datetime 或 expression 的分钟部分。
ms.openlocfilehash: 35fe1dc8d4026dd6c829a38504d9ba82d64edda2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436564"
---
# <a name="minute-function-visioshapesheet"></a>MINUTE 函数 (VisioShapeSheet)

返回一个 0 到 59 的整数，该整数表示  *datetime 或*  expression 的分钟  *部分*  。 
  
## <a name="syntax"></a>语法

MINUTE (" *datetime*  "|  *表达式*  [，  *lcid*  ])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**String** <br/> |任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**String** <br/> | 任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Number** <br/> |用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

整数
  
## <a name="remarks"></a>备注

datetime 和 expression _中的日期__组件_ 将被丢弃。 
  
无舍入过程。 如果  _datetime_ 缺失或无法转换为有效结果，函数将返回错误。 
  
返回的值根据系统当前“区域设置”中设置的时间样式设置格式。
  
MINUTE 函数还接受表达式的单个数字  _值，_ 其中小数部分表示自午夜以来的一天中的分数。 
  
## <a name="example-1"></a>示例 1

MINUTE ("7/7/1999 13：45：24") 
  
返回 45。
  
## <a name="example-2"></a>示例 2

MINUTE(TIMEVALUE("Jan. 25, 1999 12:07:45")+6 em.)
  
返回 13。
  
## <a name="example-3"></a>示例 3

MINUTE (0.575) 
  
返回 48。
  

