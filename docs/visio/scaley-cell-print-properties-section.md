---
title: ScaleY 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033788
localization_priority: Normal
ms.assetid: 02835aff-455b-ffeb-d53b-28387b6ce361
description: 指定绘图页在打印纸上的比例百分比。
ms.openlocfilehash: 0f8e86675a039002b60438eac7df92f4a2b13b98
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342726"
---
# <a name="scaley-cell-print-properties-section"></a>ScaleY 单元格（“Print Properties”内容）

指定绘图页在打印纸上的比例百分比。
  
## <a name="remarks"></a>注解

只有在 OnPage 单元格的值为 FALSE 时才使用此值。 ScaleX 和 ScaleY 单元格的值始终相同, 这与 "**页面设置**" 对话框 (在 "**设计**" 选项卡上, 单击 "**页面设置**" 箭头) 的 "**打印设置**" 选项卡上的 "**调整为**" 设置中的值相对应。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ScaleY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ScaleY  <br/> |
   
若要从某个程序按索引获取对 ScaleY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPrintProperties** <br/> |
|单元格索引：  <br/> |**visPrintPropertiesScaleY** <br/> |
   

