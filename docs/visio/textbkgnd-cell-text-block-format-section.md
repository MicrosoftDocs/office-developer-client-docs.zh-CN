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
ms.openlocfilehash: 2256a4c89812924af820c020c225f4b82b1d4856
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781510"
---
# <a name="textbkgnd-cell-text-block-format-section"></a>TextBkgnd 单元格（“Text Block Format”部分）

确定一个形状的文本背景色。
  
## <a name="remarks"></a>注解

TextBkgnd 单元格可以具有任何值从 0 到 24 或 255。 值 0 和 255 ( *visTxtBlklOpaque*) 指示透明的文本背景。 
  
若要输入自定义颜色，使用 RGB 或 HSL 函数加 1 — 例如，RGB (255,127,255) + 1。 自定义颜色的值为 RGB 颜色，并且 RGB （ *r、 g、 b*） + 1，而不是一个号码，将显示在 ShapeSheet 窗口中。 中的数字运算使用时，自定义颜色具有值将大于或等于 25。 
  
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
   

