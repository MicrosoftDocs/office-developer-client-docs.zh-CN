---
title: SketchLineWeight 单元格 ("其他效果属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6cb838be-1d6d-48e1-8e9e-bd126f0c2385
description: 确定作为素描效果的结果添加到线条粗细的额外厚度, 以从0到50的磅为单位。 当 SketchLineWeight 单元格的值增加时, 该形状的线条的粗细将增加。
ms.openlocfilehash: 0ee71bbaec59f5c79b72314b08478f8028b4e0ba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404510"
---
# <a name="sketchlineweight-cell-additional-effect-properties-section"></a>SketchLineWeight 单元格 ("其他效果属性" 部分)

确定作为素描效果的结果添加到线条粗细的额外厚度, 以从0到50的磅为单位。 当**SketchLineWeight**单元格的值增加时, 该形状的线条的粗细将增加。 
  
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**SketchLineWeight**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SketchLineWeight  <br/> |
   
若要从某个程序按索引获取对**SketchLineWeight**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSketchLineWeight** <br/> |
   

