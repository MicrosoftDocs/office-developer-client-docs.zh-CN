---
title: SketchLineChange 单元格 （其他效果属性内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 39192535-b55b-4c49-b63f-edb542c7a2e5
description: 确定随机选择的形状的线条从形状的几何量时使用素描效果的部分的长度的百分比。 如果 SketchLineChange 单元格的值设置为 0%的几何形状的行匹配形状的几何图形。 如果值为 100%的几何形状的线条不遵循的几何形状。
ms.openlocfilehash: 57d2af1a914710d7e5a58686b577014ceb7af424
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781374"
---
# <a name="sketchlinechange-cell-additional-effect-properties-section"></a>SketchLineChange 单元格 （其他效果属性内容）

确定随机选择的形状的线条从形状的几何量时使用素描效果的部分的长度的百分比。 如果**SketchLineChange**单元格的值设置为 0%的几何形状的行匹配形状的几何图形。 如果值为 100%的几何形状的线条不遵循的几何形状。 
  
## <a name="remarks"></a>备注

为了获得最佳结果，理想**SketchLineChange**单元格的值的范围是 15%到 50%之间。 15%下面的值是几乎可以忽略;大于 50%的值可能太多 randomize 行。 
  
要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**SketchLineChange**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SketchLineChange  <br/> |
   
若要从某个程序按索引获取对**SketchLineChange**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSketchLineChange** <br/> |
   

