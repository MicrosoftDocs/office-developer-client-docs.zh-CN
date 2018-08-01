---
title: ReplaceCopyCells 单元格（“Change Shape Behavior”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f36aefd-da49-47ea-9b90-2fa1a2298849
description: 指示从复制旧的形状的替换形状到形状替换操作期间 ShapeSheet 中的单元格的列表。
ms.openlocfilehash: 1e3b5e4dbc29372f75b7a7ed8013a7dd82d94e1d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781058"
---
# <a name="replacecopycells-cell-change-shape-behavior-section"></a>ReplaceCopyCells 单元格（“Change Shape Behavior”部分）

指示从复制旧的形状的替换形状到形状替换操作期间 ShapeSheet 中的单元格的列表。 
  
## <a name="remarks"></a>说明

替换为相应的主控形状必须包含**DEPENDSON**函数调用**ReplaceCopyCells**单元格中，其中函数中的每个参数都是单元格的引用。 对这些单元格从旧形状复制到的形状的形状替换操作，而不考虑它们在 ShapeSheet 中的位置的结果。 
  
值和/或引用的其他单元格的公式复制到生成的形状。 如果在生成的形状没有引用的单元格，复制单元格包含值仅。 
  
中**ReplaceCopyCells**单元格的引用重写保护组中**Protection**内容的**ReplaceLockFormat**、 **ReplaceLockShapeData**和**ReplaceLockText**单元格定义的单元格。 
  
要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ReplaceCopyCells**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReplaceCopyCells  <br/> |
   
若要从某个程序按索引获取对**ReplaceCopyCells**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowReplaceBehaviors** <br/> |
| 单元格索引：  <br/> |**visReplaceCopyCells** <br/> |
   

