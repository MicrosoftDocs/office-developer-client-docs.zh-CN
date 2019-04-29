---
title: ThemeIndex 单元格 ("主题属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21002267-1400-4398-b937-f5b289cf0ed2
description: 将应用于文档的内置 Microsoft Visio 主题的枚举存储为一个整数。 为文档选择新主题时, 将使用内置主题的索引更新文档的 ThemeIndex 单元格以及它包含的所有页面和形状。
ms.openlocfilehash: 6ddede864a54fbd7127552499d3ee1ae3d36efc1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411909"
---
# <a name="themeindex-cell-theme-properties-section"></a>ThemeIndex 单元格 ("主题属性" 部分)

将应用于文档的内置 Microsoft Visio 主题的枚举存储为一个整数。 为文档选择新主题时, 将使用内置主题的索引更新文档的**ThemeIndex**单元格以及它包含的所有页面和形状。 
  
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**ThemeIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ThemeIndex  <br/> |
   
若要从某个程序按索引获取对**ThemeIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowThemeProperties** <br/> |
| 单元格索引：  <br/> |**visThemeIndex** <br/> |
   

