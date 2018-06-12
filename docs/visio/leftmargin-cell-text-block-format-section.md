---
title: LeftMargin 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251265
localization_priority: Normal
ms.assetid: 47d84d7d-08a0-1934-d156-702da848e01c
description: 确定文本块左边框和它所包含的文本之间的距离。默认值是 0.1 英寸。此值与绘图比例无关。即使绘图比例进行调整，左边距仍保持不变。
ms.openlocfilehash: d24ba33bffea1529490b49e105fec5d01cd828b2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780554"
---
# <a name="leftmargin-cell-text-block-format-section"></a>LeftMargin 单元格（“Text Block Format”内容）

确定文本块左边框和它所包含的文本之间的距离。默认值是 0.1 英寸。此值与绘图比例无关。即使绘图比例进行调整，左边距仍保持不变。
  
## <a name="remarks"></a>注释

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LeftMargin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LeftMargin  <br/> |
   
若要从某个程序按索引获取对 LeftMargin 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowText** <br/> |
| 单元格索引：  <br/> |**visTxtBlkLeftMargin** <br/> |
   

