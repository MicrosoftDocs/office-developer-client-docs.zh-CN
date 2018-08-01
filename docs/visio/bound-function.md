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
ms.openlocfilehash: 2f6228828fee8fa1831bb0d3a714fca068808652
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779818"
---
# <a name="bound-function"></a>BOUND 函数

将某个单元格的值约束在某一范围或一组范围内。
  
## <a name="syntax"></a>语法

绑定 (* **值** *，* **类型** *，* **忽略** *，* * *value1* * *，* * *value2* * * * * * [，ignore(n) value1(n)、 value2(n)，...] * * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _value_ <br/> |必需  <br/> |**Numeric** <br/> |受到约束的当前值。  <br/> |
| _type_ <br/> |必需  <br/> |**Numeric** <br/> |约束的类型是包含 (0)、不包含 (1) 还是禁用 (2)。
  <br/> |
| _忽略_ <br/> |必需  <br/> |**Boolean** <br/> | 为 true，则忽略该范围;若要将限制到区域单元格的值，则为 FALSE。  <br/> |
| _value1_ <br/> |必需  <br/> |**Numeric** <br/> |范围内的第一个值。
  <br/> |
| _value2_ <br/> |必需  <br/> |**Numeric** <br/> |范围内的第二个值。  <br/> |
   
## <a name="remarks"></a>注解

使用 BOUND 的函数来限制单元格的值在上限和下限，例如，来控制上方或下方最小值或最大高度不应拉伸的对象。 该约束可以包含或排除相对于范围或范围。 如果不应约束的当前值，设置_type_参数为 2 （禁用）。 
  
通过提供的_忽略_、 _value1_，和_value2_参数的多个匹配项，您可以定义多个区域。 使用_忽略_参数禁用特定范围约束。 
  
包含 BOUND 的函数的公式不会被覆盖时更改其值;而是保留公式和新值放入_value_参数。 
  
## <a name="example-1"></a>示例 1

本示例使用 BOUND 函数强制控制手柄始终处于形状的边框内。 
  
Controls.X1 = 绑定 (宽度\*0.5，0，FALSE、 宽度\*0，宽度\*1)
  
Controls.Y1 = 绑定 (高度\*0.5，0，FALSE、 高度\*0，高度\*1)
  
## <a name="example-2"></a>示例 2

本示例使用 BOUND 函数将形状的宽度限制为 2 英寸、4 英寸或 6 英寸。 
  
Width = BOUND(, 0, FALSE, 2 in, 2 in, FALSE, 4 in, 4 in, FALSE, 6 in, 6 in)
  

