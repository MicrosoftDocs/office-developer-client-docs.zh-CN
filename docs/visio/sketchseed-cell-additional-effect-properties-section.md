---
title: 'SketchSeed Cell (Additional Effect Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f62650d-36f8-4c6e-b79f-c9c397a5954d
description: 表示用于确定草图效果的几何图形的随机化值，为正整数。 当将草图效果应用于形状时，将随机创建 SketchSeed 单元格的值。
ms.openlocfilehash: 3ec58fbfa183d1a6d7bb6960672658f9a6cca073
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434394"
---
# <a name="sketchseed-cell-additional-effect-properties-section"></a>SketchSeed Cell (Additional Effect Properties Section) 

表示用于确定草图效果的几何图形的随机化值，为正整数。 当将草图效果应用于形状时，将随机创建 **SketchSeed** 单元格的值。 
  
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **SketchSeed** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SketchSeed  <br/> |
   
若要从程序按索引获取对 **SketchSeed** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSketchSeed** <br/> |
   

