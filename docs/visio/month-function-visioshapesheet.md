---
title: MONTH 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251467
localization_priority: Normal
ms.assetid: e099dbb3-c591-d934-5cfd-7728b10bd8dc
description: 返回一个 1 到 12 的整数，该整数表示一个月。
ms.openlocfilehash: 71ecc7992839c871780e9b703377db37279246e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431972"
---
# <a name="month-function-visioshapesheet"></a>MONTH 函数 (VisioShapeSheet)

返回一个 1 到 12 的整数，该整数表示一个月。
  
## <a name="syntax"></a>语法

MONTH (" ** *datetime* ** "|** *expression* ** [， ** *lcid* ** ])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _datetime_ <br/> |必需  <br/> |**String** <br/> |任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。  <br/> |
| _expression_ <br/> |必需  <br/> |**String** <br/> | 任何生成日期和时间的表达式。  <br/> |
| _lcid_ <br/> |可选  <br/> |**Number** <br/> |用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。  <br/> |
   
### <a name="return-value"></a>返回值

整数
  
## <a name="remarks"></a>备注

datetime 或 _expression_ 的时间部分将被丢弃。 
  
无舍入过程。如果输入的字符串缺失或无法转换为有效的结果，则 MONTH 函数将返回错误。
  
返回的值根据系统当前“区域设置”中的短日期样式设置格式。
  
MONTH 函数还接受表达式的单个数值，其中结果的整数部分表示自 1899 年 12 月 30 日起的天数。 
  
## <a name="example-1"></a>示例 1

MONTH("May 30, 1999 13:45:24")
  
返回 5。
  
## <a name="example-2"></a>示例 2

MONTH(DATEVALUE("May 30, 1999")+7 ed.)
  
返回 6。
  
## <a name="example-3"></a>示例 3

MONTH (35580.6337) 
  
返回 5。
  

