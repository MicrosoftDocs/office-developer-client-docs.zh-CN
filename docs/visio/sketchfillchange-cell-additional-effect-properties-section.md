---
title: SketchFillChange 单元格（“Additional Effect Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 939f8f90-dee5-4175-b32a-e2964eb40681
description: 确定从形状的几何形状的填充的随机量时素描效果，使用的部分的长度的百分比。 如果 SketchFillChange 单元格的值设置为 0%，边界的形状的填充几何匹配形状的几何图形。 如果值为 100%，边界的形状的填充几何不遵循的几何形状。
ms.openlocfilehash: 8dda34e03188909e167a4abda6f62da3d43c4dd7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781379"
---
# <a name="sketchfillchange-cell-additional-effect-properties-section"></a>SketchFillChange 单元格（“Additional Effect Properties”部分）

确定从形状的几何形状的填充的随机量时素描效果，使用的部分的长度的百分比。 如果**SketchFillChange**单元格的值设置为 0%，边界的形状的填充几何匹配形状的几何图形。 如果值为 100%，边界的形状的填充几何不遵循的几何形状。 
  
## <a name="remarks"></a>说明

为了获得最佳结果，理想**SketchFillChange**单元格的值的范围是 15%到 50%之间。 15%下面的值是几乎可以忽略;大于 50%的值是越来越多随机选择。 
  
要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**SketchFillChange**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SketchFillChange  <br/> |
   
若要从某个程序按索引获取对**SketchFillChange**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSketchFillChange** <br/> |
   

