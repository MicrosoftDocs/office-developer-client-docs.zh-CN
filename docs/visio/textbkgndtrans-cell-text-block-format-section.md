---
title: TextBkgndTrans 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253240
localization_priority: Normal
ms.assetid: b2f9d317-cc42-bec5-66f9-f988bcbdcc24
description: 确定形状的文本块背景色的透明度级别。
ms.openlocfilehash: f4c4dc7700c553bd4c9bee337220e357c4c5538a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408689"
---
# <a name="textbkgndtrans-cell-text-block-format-section"></a>TextBkgndTrans 单元格（“Text Block Format”内容）

确定形状的文本块背景色的透明度级别。
  
|**值**|**说明**|
|:-----|:-----|
|0 - 100  <br/> |表示透明度的百分比。默认值为 0%（完全不透明）。  <br/> |
   
## <a name="remarks"></a>备注

这些值被四舍五入为最接近的 0.5 个百分点。值 100% 是完全透明。虽然文本背景完全透明的形状在绘图页上看起来和没有文本背景的形状相同，但是它与该页上其他对象的交互方式和透明度为 0% 的形状相同。
  
您还可以使用 **“文本”** 对话框（在 **“开始”** 选项卡上，单击 **“字体”** 箭头）的 **“字体”** 选项卡上的滑块控件设置此值。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 TextBkgndTrans 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |TextBkgndTrans  <br/> |
   
若要从某个程序按索引获取对 TextBkgndTrans 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowText** <br/> |
|单元格索引：  <br/> |**visTxtBlkBkgndTrans** <br/> |
   

