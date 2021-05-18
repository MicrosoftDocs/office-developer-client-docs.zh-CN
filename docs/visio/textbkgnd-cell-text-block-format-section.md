---
title: TextBkgnd 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251267
localization_priority: Normal
ms.assetid: a238bf1c-1acd-eacd-22f3-a48acaaa4549
description: 确定一个形状的文本背景色。
ms.openlocfilehash: 2450bf0cb0e013c0f9310eacfca0f5a20e7e6063
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406540"
---
# <a name="textbkgnd-cell-text-block-format-section"></a>TextBkgnd 单元格（“Text Block Format”内容）

确定一个形状的文本背景色。
  
## <a name="remarks"></a>备注

TextBkgnd 单元格的值可以是 0 到 24 之间的任意值，或者是 255。 *visTxtBlklOpaque* (值 0 和 255) 均表示透明文本背景。 
  
若要输入自定义颜色，请使用 RGB 或 HSL 函数加 1，例如 RGB(255,127,255)+1。 自定义颜色的值是它的 RGB 颜色，RGB ( *r、g、b*) +1 而不是数字将显示在 ShapeSheet 窗口中。 在数值运算中使用自定义颜色时，其值将大于或等于 25。 
  
您可以在 TextBkgndTrans 单元格中设置文本背景色的透明度。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 TextBkgnd 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |TextBkgnd  <br/> |
   
若要从某个程序按索引获取对 TextBkgnd 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowText** <br/> |
|单元格索引：  <br/> |**visTxtBlkBkgnd** <br/> |
   

