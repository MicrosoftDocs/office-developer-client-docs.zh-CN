---
title: EffectSchemeIndex 单元格 ("主题属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 366ade40-e89f-49b6-b4be-4e4967dbacbf
description: 确定应用于形状的主题的效果方案, 以整数形式。
ms.openlocfilehash: 0d8ed18ca960868b1cd27abe517bfea99e1f2318
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321446"
---
# <a name="effectschemeindex-cell-theme-properties-section"></a>EffectSchemeIndex 单元格 ("主题属性" 部分)

确定应用于形状的主题的效果方案, 以整数形式。
  
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**EffectSchemeIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | EffectSchemeIndex  <br/> |
   
若要从某个程序按索引获取对**EffectSchemeIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowThemeProperties** <br/> |
| 单元格索引：  <br/> |* * visEffectSchemeIndex * * <br/> |
   

