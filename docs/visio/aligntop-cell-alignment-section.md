---
title: AlignTop 单元格（“Alignment”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50
localization_priority: Normal
ms.assetid: 56e0b544-8504-0fbb-5810-7cf94d775f7c
description: 确定形状的上边框依其对齐的水平参考线或辅助点的垂直位置（该位置是相对于其父级的原点而言的）。
ms.openlocfilehash: a52527b8a0ef6398f475b3d6241e03afa6cd697b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406694"
---
# <a name="aligntop-cell-alignment-section"></a>AlignTop 单元格（“Alignment”内容）

确定形状的上边框依其对齐的水平参考线或辅助点的垂直位置（该位置是相对于其父级的原点而言的）。
  
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 AlignTop 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | AlignTop  <br/> |
   
要从某个程序按索引获取对 AlignTop 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowAlign** <br/> |
| 单元格索引：  <br/> |**visAlignTop** <br/> |
   

