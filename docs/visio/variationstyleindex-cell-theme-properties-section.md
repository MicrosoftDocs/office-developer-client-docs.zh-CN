---
title: VariationStyleIndex 单元格 ("主题属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 932195d5-2cb7-49f7-bc64-4ce00bf780b2
description: 以整数形式确定页面上活动主题变体的样式索引。
ms.openlocfilehash: 57d4b2493b7278064daf7b0cb986e58ebacf4be2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355886"
---
# <a name="variationstyleindex-cell-theme-properties-section"></a>VariationStyleIndex 单元格 ("主题属性" 部分)

以整数形式确定页面上活动主题变体的样式索引。
  
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**VariationStyleIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | VariationStyleIndex  <br/> |
   
若要从某个程序按索引获取对**VariationStyleIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowThemeProperties** <br/> |
| 单元格索引：  <br/> |**visVariationStyleIndex** <br/> |
   

