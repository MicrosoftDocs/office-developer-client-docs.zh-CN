---
title: SoftEdgesSize 单元格 ("其他效果属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a5cde2ca-f343-4a6e-b5d9-a1b78b3cd240
description: 确定柔化边缘效果的大小, 以磅为单位, 以0.00 到100.00。 如果 SoftEdgesSize 单元格的值为 0, 则该形状没有柔化边缘。
ms.openlocfilehash: e749fefde8e0358cbf4ab8388a61ad703c7d52ff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435913"
---
# <a name="softedgessize-cell-additional-effect-properties-section"></a>SoftEdgesSize 单元格 ("其他效果属性" 部分)

确定柔化边缘效果的大小, 以磅为单位, 以0.00 到100.00。 如果**SoftEdgesSize**单元格的值为 0, 则该形状没有柔化边缘。 
  
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**SoftEdgesSize**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SoftEdgesSize  <br/> |
   
若要从某个程序按索引获取对**SoftEdgesSize**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visSoftEdgesSize** <br/> |
   

