---
title: BottomMargin 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm120
localization_priority: Normal
ms.assetid: 3121911b-34d5-d99c-3806-76f6e2824f92
description: 确定文本块的下边框和所包含文本的最后一行之间的距离。默认值是 0.1 英寸。此值与绘图比例无关。即使绘图比例进行调整，下边距也保持不变。
ms.openlocfilehash: 544557f1e797315619bc9975db0b87a09981726c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338085"
---
# <a name="bottommargin-cell-text-block-format-section"></a>BottomMargin 单元格（“Text Block Format”内容）

确定文本块的下边框和所包含文本的最后一行之间的距离。默认值是 0.1 英寸。此值与绘图比例无关。即使绘图比例进行调整，下边距也保持不变。
  
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 BottomMargin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | BottomMargin  <br/> |
   
要从某个程序按索引获取对 BottomMargin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowText** <br/> |
| 单元格索引：  <br/> |**visTxtBlkBottomMargin** <br/> |
   

