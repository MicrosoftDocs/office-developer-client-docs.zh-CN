---
title: SketchLineChange 单元格 ("其他效果属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 39192535-b55b-4c49-b63f-edb542c7a2e5
description: 根据某一节的长度的百分比, 确定在使用草图效果时形状的几何图形中形状的线条的随机量。 如果 SketchLineChange 单元格的值设置为 0%, 则形状的线条的几何图形将与形状的几何图形相匹配。 如果值为 100%, 则形状的线条的几何图形不遵循形状的几何图形。
ms.openlocfilehash: ba57a4d2e43a91475f4c3ab4862f723eb2653a89
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315125"
---
# <a name="sketchlinechange-cell-additional-effect-properties-section"></a>SketchLineChange 单元格 ("其他效果属性" 部分)

根据某一节的长度的百分比, 确定在使用草图效果时形状的几何图形中形状的线条的随机量。 如果**SketchLineChange**单元格的值设置为 0%, 则形状的线条的几何图形将与形状的几何图形相匹配。 如果值为 100%, 则形状的线条的几何图形不遵循形状的几何图形。 
  
## <a name="remarks"></a>注解

为获得最佳结果, **SketchLineChange**单元格的理想值范围为 15% 到 50%。 小于 15% 的值几乎是显而易见的;大于 50% 的值可能会将行随机化过多。 
  
若要从另一个公式按名称获取对**SketchLineChange**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SketchLineChange  <br/> |
   
若要从某个程序按索引获取对**SketchLineChange**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSketchLineChange** <br/> |
   

