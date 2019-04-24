---
title: ShapePermeablePlace 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm885
localization_priority: Normal
ms.assetid: b647cbb5-2769-068d-bbda-2dc983c47ac9
description: 确定在“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）中排放形状时，可放置形状是否可以放置在某个形状的顶部。
ms.openlocfilehash: ceecfa25c66c3ba261865d0131a3f55ef444d5e8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357055"
---
# <a name="shapepermeableplace-cell-shape-layout-section"></a>ShapePermeablePlace 单元格（“Shape Layout”内容）

确定在 **“配置布局”** 对话框（在 **“设计”** 选项卡上的 **“布局”** 组中，单击 **“重新布局页面”**，然后单击 **“其他布局选项”**）中排放形状时，可放置形状是否可以放置在某个形状的顶部。
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> |使形状能够放置在某个形状的顶部。  <br/> |
|FALSE  <br/> |使形状不能放置在某个形状的顶部。  <br/> |
   
## <a name="remarks"></a>注解

您还可以在 "**行为**" 对话框 (在 "[开发工具](run-in-developer-mode-display-the-developer-tab.md)" 选项卡上的 "**形状设计**" 组中, 单击 "**行为**", 然后单击 "**位置**" 选项卡) 中的 "**放置**" 选项卡上设置此单元格的值。). 
  
在 Visio 2000 之前的版本中，您可以使用“Miscellaneous”内容中的 ObjInteract 单元格设置此行为。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapePermeablePlace 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapePermeablePlace  <br/> |
   
若要从某个程序按索引获取对 ShapePermeablePlace 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOPermeablePlace** <br/> |
   

