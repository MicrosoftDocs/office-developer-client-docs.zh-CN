---
title: SoftEdgesSize 单元格（“Additional Effect Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a5cde2ca-f343-4a6e-b5d9-a1b78b3cd240
description: 确定柔化边缘效果，以向 100.00 0.00 从磅为单位的大小。 如果 SoftEdgesSize 单元格的值为 0，则该形状没有柔化边缘。
ms.openlocfilehash: 3b301ae2e8c82867be2a486f2e93c2275fbf3914
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781407"
---
# <a name="softedgessize-cell-additional-effect-properties-section"></a>SoftEdgesSize 单元格（“Additional Effect Properties”部分）

确定柔化边缘效果，以向 100.00 0.00 从磅为单位的大小。 如果**SoftEdgesSize**单元格的值为 0，则该形状没有柔化边缘。 
  
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**SoftEdgesSize**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SoftEdgesSize  <br/> |
   
若要从某个程序按索引获取对**SoftEdgesSize**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSoftEdgesSize** <br/> |
   

