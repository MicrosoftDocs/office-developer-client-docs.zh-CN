---
title: 'SoftEdgesSize Cell (Additional Effect Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a5cde2ca-f343-4a6e-b5d9-a1b78b3cd240
description: 确定柔化边缘效果的大小，以 0.00 到 100.00 的点表示。 如果 SoftEdgesSize 单元格的值为 0，则形状没有柔化边缘。
ms.openlocfilehash: e749fefde8e0358cbf4ab8388a61ad703c7d52ff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435913"
---
# <a name="softedgessize-cell-additional-effect-properties-section"></a>SoftEdgesSize Cell (Additional Effect Properties Section) 

确定柔化边缘效果的大小，以 0.00 到 100.00 的点表示。 如果 **SoftEdgesSize** 单元格的值为 0，则形状没有柔化边缘。 
  
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **SoftEdgesSize** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SoftEdgesSize  <br/> |
   
若要从程序按索引获取对 **SoftEdgesSize** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSoftEdgesSize** <br/> |
   

