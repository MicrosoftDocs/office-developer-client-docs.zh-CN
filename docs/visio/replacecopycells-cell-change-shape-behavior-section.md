---
title: 'ReplaceCopyCells Cell (Change Shape Behavior Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f36aefd-da49-47ea-9b90-2fa1a2298849
description: 指示 ShapeSheet 中的单元格列表，这些单元格在形状替换操作过程中从旧形状复制到替换形状。
ms.openlocfilehash: f2a7908a623c861d0284821b2d8ae5fc71690685
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409340"
---
# <a name="replacecopycells-cell-change-shape-behavior-section"></a>ReplaceCopyCells Cell (Change Shape Behavior Section) 

指示 ShapeSheet 中的单元格列表，这些单元格在形状替换操作过程中从旧形状复制到替换形状。 
  
## <a name="remarks"></a>备注

替换的主形状必须在 **ReplaceCopyCells** 单元格中包含 **DEPENDSON** 函数调用，其中函数的每个参数都是对单元格的引用。 这些单元格从旧形状复制到由形状替换操作产生的形状，而不管它们在 ShapeSheet 中在哪里。 
  
引用其他单元格的值和/或公式将复制到生成的形状。 如果生成的形状没有引用的单元格，则复制的单元格仅包含值。 
  
**ReplaceCopyCells** 单元格中的引用会覆盖在"保护"部分以及 **ReplaceLockFormat、ReplaceLockShapeData** 和 **ReplaceLockText** 单元格中定义的单元格上设置的保护。  
  
若要从另一个公式、Cell 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **ReplaceCopyCells** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReplaceCopyCells  <br/> |
   
若要从程序按索引获取 **对 ReplaceCopyCells** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowReplaceBehaviors** <br/> |
| 单元格索引：  <br/> |**visReplaceCopyCells** <br/> |
   

