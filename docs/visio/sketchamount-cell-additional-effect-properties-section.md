---
title: SketchAmount 单元格 ("其他效果属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7c7353b7-f28e-4004-bf13-6e9714fbed37
description: 确定草图效果的扭曲量, 以0到25之间的整数表示。
ms.openlocfilehash: fd9ee3390d05f24d81d9c6677160155b0f0f0d35
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404419"
---
# <a name="sketchamount-cell-additional-effect-properties-section"></a>SketchAmount 单元格 ("其他效果属性" 部分)

确定草图效果的扭曲量, 以0到25之间的整数表示。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |形状没有应用的素描效果。  <br/> |
|1-25  <br/> |形状应用了 "素描扭曲", 其中值1是最大的扭曲, 25 为最小。  <br/> |
   
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**SketchAmount**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SketchAmount  <br/> |
   
若要从某个程序按索引获取对**SketchAmount**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSketchAmount** <br/> |
   

