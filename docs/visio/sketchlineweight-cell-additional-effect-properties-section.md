---
title: SketchLineWeight 单元格（“Additional Effect Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6cb838be-1d6d-48e1-8e9e-bd126f0c2385
description: 确定其他粗细素描效果，以从 0 到 50 磅的结果添加到线条粗细。 形状的线条的粗细随着 SketchLineWeight 增加单元格的值。
ms.openlocfilehash: 9ab99faab907ddf0d944abbeea39672906b4c03d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781391"
---
# <a name="sketchlineweight-cell-additional-effect-properties-section"></a>SketchLineWeight 单元格（“Additional Effect Properties”部分）

确定其他粗细素描效果，以从 0 到 50 磅的结果添加到线条粗细。 形状的线条的粗细随着**SketchLineWeight**单元格增加的值。 
  
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**SketchLineWeight**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SketchLineWeight  <br/> |
   
若要从某个程序按索引获取对**SketchLineWeight**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSketchLineWeight** <br/> |
   

