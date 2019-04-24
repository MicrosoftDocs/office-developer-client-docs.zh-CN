---
title: ShapePermeableX 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm890
localization_priority: Normal
ms.assetid: 7e27b36c-4fd1-34e0-c168-f49eb5757b0e
description: 确定连接线是否可以水平穿绕可放置形状。
ms.openlocfilehash: 21fa1683c4b1afd24992ec7a8a6daa52a8280825
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357048"
---
# <a name="shapepermeablex-cell-shape-layout-section"></a>ShapePermeableX 单元格（“Shape Layout”内容）

确定连接线是否可以水平穿绕可放置形状。
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> |允许连接线水平穿绕可放置形状。  <br/> |
|FALSE  <br/> |不允许连接线水平穿绕可放置形状。  <br/> |
   
## <a name="remarks"></a>注解

您还可以在 "**行为**" 对话框 (在 "[开发工具](run-in-developer-mode-display-the-developer-tab.md)" 选项卡上的 "**形状设计**" 组中, 单击 "**行为**", 然后单击 "**位置**" 选项卡) 中的 "**放置**" 选项卡上设置此单元格的值。). 
  
在 Visio 2000 之前的版本中，您可以使用“Miscellaneous”内容中的 ObjInteract 单元格设置此行为。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapePermeableX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapePermeableX  <br/> |
   
若要从某个程序按索引获取对 ShapePermeableX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOPermX** <br/> |
   

