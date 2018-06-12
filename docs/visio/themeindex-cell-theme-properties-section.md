---
title: ThemeIndex 单元格 (主题 Properties)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21002267-1400-4398-b937-f5b289cf0ed2
description: 存储内置 Microsoft Visio 主题应用于文档，作为整数的枚举。 当文档选择新主题时，文档和所有页面和形状及其包含的 ThemeIndex 单元格的内置的主题的索引的更新。
ms.openlocfilehash: 8a9202631bc4d9131d52dea1f852983e1d7528e5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781505"
---
# <a name="themeindex-cell-theme-properties-section"></a>ThemeIndex 单元格 (主题 Properties)

存储内置 Microsoft Visio 主题应用于文档，作为整数的枚举。 当新主题选择文档，文档的**ThemeIndex**单元格和所有页面和它包含的形状的内置的主题的索引的都更新。 
  
## <a name="remarks"></a>备注

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ThemeIndex**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ThemeIndex  <br/> |
   
若要从某个程序按索引获取对**ThemeIndex**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowThemeProperties** <br/> |
| 单元格索引：  <br/> |**visThemeIndex** <br/> |
   

