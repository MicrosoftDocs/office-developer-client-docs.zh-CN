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
description: '如果 cellreference 的值为错误类型，则返回 TRUE #VALUE，其中公式中的参数类型错误。 ISERRVALUE 函数用于引用另一个单元格的逻辑表达式。'
ms.openlocfilehash: 62058522dc8a2387aec9867e4892da740aba9b44
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404426"
---
# <a name="iserrvalue-function"></a>ISERRVALUE 函数

如果  _cellreference_ 的值为错误类型，则返回 TRUE #VALUE，其中公式中的参数类型错误。 ISERRVALUE 函数用于引用另一个单元格的逻辑表达式。 
  
## <a name="syntax"></a>语法

ISERRVALUE (** *cellreference* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellreference_ <br/> |必需  <br/> |**String** <br/> |对单元格的引用。  <br/> |
   
## <a name="remarks"></a>备注

Scratch 单元格 A 到 D 不会返回 #VALUE! 错误，因为该公式可以在同一字符串中包含数字和字母。单元格 X 和 Y 必须只包含数字。 
  
## <a name="example-1"></a>示例 1

|**Cell**|**公式**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.X1  <br/> |= "House"  <br/> |#VALUE!  <br/> |
|Scratch.A1  <br/> |= If (ISERRVALUE(Scratch.X1),2,Scratch.X1)  <br/> |2  <br/> |
   
返回 2，因为返回的值是 #VALUE! 错误，而表达式指示 Microsoft Visio 在出现错误时返回 2。
  
## <a name="example-2"></a>示例 2

|**Cell**|**公式**|**返回的值**|
|:-----|:-----|:-----|
|Scratch.A1  <br/> |="5 + 7"  <br/> |5 + 7  <br/> |
|Scratch.B1  <br/> |=If (ISERRVALUE(Scratch.A1),2,Scratch.A1)  <br/> |5 + 7  <br/> |
   
返回 12，因为返回的值不是 #VALUE! 错误，而表达式指示 Visio 返回原始单元格的值。
  

