---
title: ReplaceCopyCells 单元格 ("更改形状行为" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f36aefd-da49-47ea-9b90-2fa1a2298849
description: 指示在形状替换操作过程中从一个旧形状复制到替换形状的 ShapeSheet 中的单元格列表。
ms.openlocfilehash: f2a7908a623c861d0284821b2d8ae5fc71690685
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320172"
---
# <a name="replacecopycells-cell-change-shape-behavior-section"></a>ReplaceCopyCells 单元格 ("更改形状行为" 部分)

指示在形状替换操作过程中从一个旧形状复制到替换形状的 ShapeSheet 中的单元格列表。 
  
## <a name="remarks"></a>注解

替换的主控形状必须包含**ReplaceCopyCells**单元格中的**DEPENDSON**函数调用, 其中函数中的每个参数都是对单元格的引用。 将这些单元格从旧形状复制到形状替换操作产生的形状, 而不考虑它们在 ShapeSheet 中的位置。 
  
引用其他单元格的值和/或公式将复制到生成的形状中。 如果生成的形状没有被引用的单元格, 则复制的单元格只包含值。 
  
**ReplaceCopyCells**单元格的引用在 "**保护**" 部分和 " **ReplaceLockFormat**"、" **ReplaceLockShapeData**" 和 " **ReplaceLockText** " 单元格中定义的单元格上覆盖保护集。 
  
若要从另一个公式按名称获取对**ReplaceCopyCells**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReplaceCopyCells  <br/> |
   
若要从某个程序按索引获取对**ReplaceCopyCells**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowReplaceBehaviors** <br/> |
| 单元格索引：  <br/> |**visReplaceCopyCells** <br/> |
   

