---
title: 'SketchLineChange Cell (Additional Effect Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 39192535-b55b-4c49-b63f-edb542c7a2e5
description: 确定使用草图效果时形状的几何图形线条的随机化量，以部分长度的百分比表示。 如果 SketchLineChange 单元格的值设置为 0%，则形状线条的几何图形与形状的几何图形匹配。 如果值为 100%，则形状线条的几何图形不遵循形状的几何图形。
ms.openlocfilehash: ba57a4d2e43a91475f4c3ab4862f723eb2653a89
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419504"
---
# <a name="sketchlinechange-cell-additional-effect-properties-section"></a>SketchLineChange Cell (Additional Effect Properties Section) 

确定使用草图效果时形状的几何图形线条的随机化量，以部分长度的百分比表示。 如果 **SketchLineChange** 单元格的值设置为 0%，则形状线条的几何图形与形状的几何图形匹配。 如果值为 100%，则形状线条的几何图形不遵循形状的几何图形。 
  
## <a name="remarks"></a>备注

为了获得最佳结果 **，SketchLineChange** 单元格的理想值范围介于 15% 到 50% 之间。 低于 15% 的值几乎不明显;大于 50% 的值可能会过多地随机化该行。 
  
若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **SketchLineChange** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SketchLineChange  <br/> |
   
若要从程序按索引获取 **对 SketchLineChange** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSketchLineChange** <br/> |
   

