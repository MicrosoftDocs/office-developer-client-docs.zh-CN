---
title: 'SketchLineWeight Cell (Additional Effect Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6cb838be-1d6d-48e1-8e9e-bd126f0c2385
description: 确定作为草图效果的结果添加到线条粗细的额外粗细（以 0 到 50 磅）。 随着 SketchLineWeight 单元格值的增加，形状线条的粗细增加。
ms.openlocfilehash: 0ee71bbaec59f5c79b72314b08478f8028b4e0ba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404510"
---
# <a name="sketchlineweight-cell-additional-effect-properties-section"></a>SketchLineWeight Cell (Additional Effect Properties Section) 

确定作为草图效果的结果添加到线条粗细的额外粗细（以 0 到 50 磅）。 随着 **SketchLineWeight** 单元格值的增加，形状线条的粗细增加。 
  
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **SketchLineWeight** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SketchLineWeight  <br/> |
   
若要从程序按索引获取 **对 SketchLineWeight** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSketchLineWeight** <br/> |
   

