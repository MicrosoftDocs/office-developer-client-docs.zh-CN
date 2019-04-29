---
title: AlignRight 单元格（“Alignment”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251297
localization_priority: Normal
ms.assetid: c6d298a4-1602-a53c-bb5d-2ef16b43f722
description: 确定形状的右边框依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。
ms.openlocfilehash: 558808908107a3e42d9d6e4a6fc1cf177150edb9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439770"
---
# <a name="alignright-cell-alignment-section"></a>AlignRight 单元格（“Alignment”内容）

确定形状的右边框依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 AlignRight 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | AlignRight  <br/> |
   
要从某个程序按索引获取对 AlignRight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowAlign** <br/> |
| 单元格索引：  <br/> |**visAlignRight** <br/> |
   

