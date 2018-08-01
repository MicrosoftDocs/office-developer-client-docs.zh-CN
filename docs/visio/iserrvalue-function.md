---
title: ISERRVALUE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251453
localization_priority: Normal
ms.assetid: c7feec6f-f47a-60ee-b056-7b2dc51ed9a9
description: 'Cellreference 的值为错误时为 TRUE 的返回类型的 #VALUE，其中公式中的参数是错误的类型。 ISERRVALUE 函数引用另一个单元格的逻辑表达式中使用。'
ms.openlocfilehash: 50c501cc404d9c5f80e0bd1261b3d3bcd7087de2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780492"
---
# <a name="iserrvalue-function"></a>ISERRVALUE 函数

_Cellreference_的值为错误时为 TRUE 的返回类型的 #VALUE，其中公式中的参数是错误的类型。 ISERRVALUE 函数引用另一个单元格的逻辑表达式中使用。 
  
## <a name="syntax"></a>语法

ISERRVALUE (* * *cellreference* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellreference_ <br/> |必需  <br/> |**字符串** <br/> |对单元格的引用。  <br/> |
   
## <a name="remarks"></a>注解

Scratch 单元格 A 到 D 不会返回 #VALUE! 错误，因为该公式可以在同一字符串中包含数字和字母。单元格 X 和 Y 必须只包含数字。 
  
## <a name="example-1"></a>示例 1

|**Cell**|**Formula**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.X1  <br/> |= "House"  <br/> |#VALUE!  <br/> |
|Scratch.A1  <br/> |= If (ISERRVALUE(Scratch.X1),2,Scratch.X1)  <br/> |2  <br/> |
   
返回 2，因为返回的值是 #VALUE! 错误，而表达式指示 Microsoft Visio 在出现错误时返回 2。
  
## <a name="example-2"></a>示例 2

|**Cell**|**Formula**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.A1  <br/> |="5 + 7"  <br/> |5 + 7  <br/> |
|Scratch.B1  <br/> |=If (ISERRVALUE(Scratch.A1),2,Scratch.A1)  <br/> |5 + 7  <br/> |
   
返回 12，因为返回的值不是 #VALUE! 错误，而表达式指示 Visio 返回原始单元格的值。
  

