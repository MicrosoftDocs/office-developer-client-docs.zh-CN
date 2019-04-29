---
title: TheText 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1005
localization_priority: Normal
ms.assetid: 2d63768e-afdb-4b3f-de49-f9ba69ae5391
description: 当形状文本或文本组成成分改变时进行求值的事件单元格。
ms.openlocfilehash: 6aa5e14f339d0030d8421eaae62b0e481be91fc7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435164"
---
# <a name="thetext-cell-events-section"></a>TheText 单元格（“Events”内容）

当形状文本或文本组成成分改变时进行求值的事件单元格。
  
## <a name="remarks"></a>说明

只在事件发生后（而非输入公式后）才对事件单元格求值。您可以使用 TheText 单元格触发重新计算，例如，用 TEXTWIDTH( ) 和 TEXTHEIGHT( ) 函数重新计算文本宽度和高度。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TheText 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TheText  <br/> |
   
要从某个程序按索引获取对 TheText 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowEvent** <br/> |
| 单元格索引：  <br/> |**visEvtCellTheText** <br/> |
   

