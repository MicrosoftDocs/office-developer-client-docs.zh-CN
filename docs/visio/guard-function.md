---
title: GUARD 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251435
localization_priority: Normal
ms.assetid: 6c85414c-9fb6-cdc5-f5b6-8eb13c9608af
description: 保护表达式被删除和更改执行的动作在绘图窗口，例如，移动，尺寸调整、 分组或取消组合形状。
ms.openlocfilehash: fd5fcfbe11eb054dfa625834640c0280cae96c3f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780362"
---
# <a name="guard-function"></a>GUARD 函数

保护*表达式*被删除和更改执行的动作在绘图窗口，例如，移动，尺寸调整、 分组或取消组合形状。 
  
## <a name="syntax"></a>语法

GUARD (* **表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**字符串** <br/> |常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。  <br/> |
   
## <a name="remarks"></a>注解

最容易受 GUARD 函数影响的单元格是“Height”、“Width”、“PinX”和“PinY”。 
  
在任意单元格中保护一个公式可以防止该单元格的值被绘图窗口中的动作所改变。然而，绘图窗口中的一个动作可能影响几个单元格，如果您想要防止形状的外观发生意外的改变，这些单元格必须都受到保护。 
  
## <a name="example"></a>示例

GUARD(TEXTWIDTH(TheText) + 0.5 in) 
  
形状的“Shape Transform”内容中的 Width 单元格中的此表达式可以防止当绘图窗口中形状的宽度改变时，表达式 (TEXTWIDTH(TheText) + 0.5 in) 被其他值替换。TheText 是关联形状的文本构成改变时所触发的单元格。 
  

