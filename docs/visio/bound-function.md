---
title: BOUND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60099
localization_priority: Normal
ms.assetid: 36374d78-1028-bd7f-6282-66555ee31306
description: 将某个单元格的值约束在某一范围或一组范围内。
ms.openlocfilehash: 85fbe66d4e458ac4e42c9eb3c65b9a3a1d8211df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425958"
---
# <a name="bound-function"></a>BOUND 函数

将某个单元格的值约束在某一范围或一组范围内。
  
## <a name="syntax"></a>语法

绑定 (* **值** *、* **类型** *、* **忽略** *、* * ** 、* *、* * *value2* * * * * * [、ignore (n)、value1 (n)、value2 (n),...] * * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _value_ <br/> |必需  <br/> |**数值** <br/> |受到约束的当前值。  <br/> |
| _type_ <br/> |必需  <br/> |**数值** <br/> |约束的类型是包含 (0)、不包含 (1) 还是禁用 (2)。  <br/> |
| _忽略_ <br/> |必需  <br/> |**Boolean** <br/> | 如果为 TRUE, 则忽略区域;如果为 FALSE, 则将单元格的值限定在区域中。  <br/> |
| _value1_ <br/> |必需  <br/> |**数值** <br/> |范围内的第一个值。  <br/> |
| _value2_ <br/> |必需  <br/> |**数值** <br/> |范围内的第二个值。  <br/> |
   
## <a name="remarks"></a>说明

使用 BOUND 函数可以将某个单元格的值限制在上限和下限之内，例如，可以控制那些不应拉伸超过最大高度或缩短小于最小高度的对象。 对于范围，该约束可以包括范围值本身或者不包括范围值本身。 如果当前值不应受约束, 请将_type_参数设置为 2 (已禁用)。 
  
您可以通过提供 " _ignore_"、" _value1_" 和 " _value2_ " 参数的多个匹配项来定义多个区域。 使用_ignore_参数禁用特定范围的约束。 
  
包含绑定函数的公式在其值发生更改时不会被覆盖;相反, 将保留公式, 并将新值放入_value_参数中。 
  
## <a name="example-1"></a>示例 1

本示例使用 BOUND 函数强制控制手柄始终处于形状的边框内。 
  
控件 X1 = 绑定 (Width\*0.5, 0, FALSE, width\*0, width\*1)
  
控件。 Y1 = 界限 (Height\*0.5, 0, FALSE, height\*0, height\*1)
  
## <a name="example-2"></a>示例 2

本示例使用 BOUND 函数将形状的宽度限制为 2 英寸、4 英寸或 6 英寸。 
  
Width = BOUND(, 0, FALSE, 2 in, 2 in, FALSE, 4 in, 4 in, FALSE, 6 in, 6 in)
  

