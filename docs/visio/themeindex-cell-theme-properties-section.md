---
title: 'ThemeIndex Cell (Theme Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21002267-1400-4398-b937-f5b289cf0ed2
description: 将应用于文档的内置 Microsoft Visio 主题的枚举存储为整数。 为文档选择新主题后，文档及其包含的所有页面和形状的 ThemeIndex 单元格将更新为内置主题的索引。
ms.openlocfilehash: 6ddede864a54fbd7127552499d3ee1ae3d36efc1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411909"
---
# <a name="themeindex-cell-theme-properties-section"></a>ThemeIndex Cell (Theme Properties Section) 

将应用于文档的内置 Microsoft Visio 主题的枚举存储为整数。 为文档选择新主题后，文档及其包含的所有页面和形状的 **ThemeIndex** 单元格将更新为内置主题的索引。 
  
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **ThemeIndex** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ThemeIndex  <br/> |
   
若要从程序按索引获取对 **ThemeIndex** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowThemeProperties** <br/> |
| 单元格索引：  <br/> |**visThemeIndex** <br/> |
   

