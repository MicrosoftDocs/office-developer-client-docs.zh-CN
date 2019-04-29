---
title: HOUR 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251437
localization_priority: Normal
ms.assetid: 2a21d6f9-bad6-92ab-6d36-477bcb9d7f17
description: 返回一个整数, 0 到 23, 表示日期时间或表达式的一天中的小时数。
ms.openlocfilehash: 1d0c6ec2bd80605401f44d2a5ef6e3d41bc72556
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429633"
---
# <a name="hour-function-visioshapesheet"></a>HOUR 函数 (VisioShapeSheet)

返回一个整数, 0 到 23, 表示_日期时间_或_表达式_的一天中的小时数。
  
## <a name="syntax"></a>语法

HOUR ("* * *datetime* * *" |* **表达式** * [, * * *lcid* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**String** <br/> | 通常被识别为表示日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**相同** <br/> |生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Number** <br/> | 用于计算非本地日期时间的区域设置标识符。 区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
## <a name="remarks"></a>说明

*datetime*和*expression*中的日期部分将被丢弃。 
  
无舍入过程。 如果*datetime*缺失或无法转换为有效结果, 函数将返回错误。 
  
返回的值根据系统当前“区域设置”中设置的时间样式设置格式。 
  
HOUR 函数还接受一个数值, 其中结果的** 小数部分表示自午夜以来的一天中的某一天。 
  
## <a name="example-1"></a>示例 1

小时 ("15:45")
  
返回 15。
  
## <a name="example-2"></a>示例 2

HOUR("May 30, 1997 3:45:24 PM")
  
返回 15。
  
## <a name="example-3"></a>示例 3

小时 (0.5)
  
返回 12。
  
## <a name="example-4"></a>示例 4

HOUR ("5/30/1997")
  
返回 0。
  

