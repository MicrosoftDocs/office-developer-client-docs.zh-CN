---
title: VariationColorIndex 单元格 ("主题属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea95a90c-4729-4689-a6f4-31dfccf37b9b
description: 以整数形式确定页面上活动主题变体的颜色索引。
ms.openlocfilehash: 7582b779fb5be6bdf3528da137b1b08b8cd9c01a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431769"
---
# <a name="variationcolorindex-cell-theme-properties-section"></a>VariationColorIndex 单元格 ("主题属性" 部分)

以整数形式确定页面上活动主题变体的颜色索引。
  
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**VariationColorIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | VariationColorIndex  <br/> |
   
若要从某个程序按索引获取对**VariationColorIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowThemeProperties** <br/> |
| 单元格索引：  <br/> |**visVariationColorIndex** <br/> |
   

