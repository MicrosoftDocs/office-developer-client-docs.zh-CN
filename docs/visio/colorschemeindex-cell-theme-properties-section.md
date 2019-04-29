---
title: ColorSchemeIndex 单元格 ("主题属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fb84f71e-59c4-43d4-a28b-c3d6f267d2ae
description: 确定形状的配色方案在其后面采用的主题的索引 (作为整数)。
ms.openlocfilehash: d67363b48454a717914b8ff9e39952609d848118
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430761"
---
# <a name="colorschemeindex-cell-theme-properties-section"></a>ColorSchemeIndex 单元格 ("主题属性" 部分)

确定形状的配色方案在其后面采用的主题的索引 (作为整数)。
  
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**ColorSchemeIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ColorSchemeIndex  <br/> |
   
若要从某个程序按索引获取对**ColorSchemeIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowThemeProperties** <br/> |
| 单元格索引：  <br/> |**visColorSchemeIndex** <br/> |
   

