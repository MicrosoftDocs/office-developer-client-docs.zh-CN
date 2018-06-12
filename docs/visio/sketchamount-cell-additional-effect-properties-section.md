---
title: SketchAmount 单元格 （其他效果属性内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7c7353b7-f28e-4004-bf13-6e9714fbed37
description: 确定为 0 到 25 之间的整数素描效果，扭曲的四量。
ms.openlocfilehash: d5ae954f2eab48722c48c9bc4b3f640403dbb3ec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781371"
---
# <a name="sketchamount-cell-additional-effect-properties-section"></a>SketchAmount 单元格 （其他效果属性内容）

确定为 0 到 25 之间的整数素描效果，扭曲的四量。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |该形状具有应用于它没有素描效果。  <br/> |
|1-25  <br/> |形状具有草图失真于，其中值为 1 是大多数失真，25 是最少。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**SketchAmount**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SketchAmount  <br/> |
   
若要从某个程序按索引获取对**SketchAmount**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSketchAmount** <br/> |
   

