---
title: IndRight 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251256
localization_priority: Normal
ms.assetid: f0891064-95d9-ae1b-28f3-3aef1406b636
description: 代表段落中所有文本行自该文本块的右边距始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，右缩进仍保持不变。
ms.openlocfilehash: e6529bf41cb8fdd40371d9a663291961626afb56
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408864"
---
# <a name="indright-cell-paragraph-section"></a>IndRight 单元格（“Paragraph”内容）

代表段落中所有文本行自该文本块的右边距始缩进的距离。此值与绘图比例无关。即使绘图比例进行调整，右缩进仍保持不变。
  
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 IndRight 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Para.IndRight[  *i*  ] 其中  *i*  = <1> 2， 3...  <br/> |
   
要从某个程序按索引获取对 IndRight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionParagraph** <br/> |
| 行索引：  <br/> |**visRowParagraph**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 单元格索引：  <br/> |**visIndentRight** <br/> |
   

