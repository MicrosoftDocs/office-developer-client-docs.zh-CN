---
title: SketchFillChange 单元格 ("其他效果属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 939f8f90-dee5-4175-b32a-e2964eb40681
description: 根据某一节的长度的百分比, 确定在使用草图效果时形状的几何图形的随机填充量。 如果 SketchFillChange 单元格的值设置为 0%, 则形状的填充的边界几何图形与形状的几何图形相匹配。 如果值为 100%, 则该形状的填充的边界几何图形不遵循形状的几何图形。
ms.openlocfilehash: 8726e9dd6ca6257fb8dbbbef3dce1d4ec344e28b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408073"
---
# <a name="sketchfillchange-cell-additional-effect-properties-section"></a>SketchFillChange 单元格 ("其他效果属性" 部分)

根据某一节的长度的百分比, 确定在使用草图效果时形状的几何图形的随机填充量。 如果**SketchFillChange**单元格的值设置为 0%, 则形状的填充的边界几何图形与形状的几何图形相匹配。 如果值为 100%, 则该形状的填充的边界几何图形不遵循形状的几何图形。 
  
## <a name="remarks"></a>说明

为获得最佳结果, **SketchFillChange**单元格的理想值范围为 15% 到 50%。 小于 15% 的值几乎是显而易见的;大于 50% 的值的随机化程度越来越高。 
  
若要从另一个公式按名称获取对**SketchFillChange**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SketchFillChange  <br/> |
   
若要从某个程序按索引获取对**SketchFillChange**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSketchFillChange** <br/> |
   

