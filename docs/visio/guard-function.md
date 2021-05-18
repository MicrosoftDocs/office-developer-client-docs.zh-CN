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
description: 防止表达式被绘图窗口中执行的操作删除和更改，例如移动形状、调整形状大小、对形状进行分组或取消组合。
ms.openlocfilehash: 0bdfa023d53e739a970cab65b1dbd67bc1a44461
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408150"
---
# <a name="guard-function"></a>GUARD 函数

防止  *表达式*  被绘图窗口中执行的操作删除和更改，例如移动形状、调整形状大小、对形状进行分组或取消组合。 
  
## <a name="syntax"></a>语法

GUARD (** *expression* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**String** <br/> |常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。  <br/> |
   
## <a name="remarks"></a>备注

最容易受 GUARD 函数影响的单元格是“Height”、“Width”、“PinX”和“PinY”。 
  
在任意单元格中保护一个公式可以防止该单元格的值被绘图窗口中的动作所改变。然而，绘图窗口中的一个动作可能影响几个单元格，如果您想要防止形状的外观发生意外的改变，这些单元格必须都受到保护。 
  
## <a name="example"></a>示例

GUARD(TEXTWIDTH(TheText) + 0.5 in) 
  
形状的“Shape Transform”内容中的 Width 单元格中的此表达式可以防止当绘图窗口中形状的宽度改变时，表达式 (TEXTWIDTH(TheText) + 0.5 in) 被其他值替换。TheText 是关联形状的文本构成改变时所触发的单元格。 
  

