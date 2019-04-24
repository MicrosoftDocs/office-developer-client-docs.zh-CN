---
title: ShapePlaceStyle 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm70007
localization_priority: Normal
ms.assetid: 29bfe8ec-ca12-8fbf-b62b-ece3710dfe2e
description: 指定在 "配置布局" 对话框 (在 "设计" 选项卡上的 "布局" 组中, 单击 "重新布局页面", 然后单击 "其他布局选项") 中排放形状时, 形状在页面上的放置方式。 存储 VisCellIndices 中的布局样式和对齐值。
ms.openlocfilehash: 381f74912b64395f33a2dc55c0bad24d36a16286
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326507"
---
# <a name="shapeplacestyle-cell-shape-layout-section"></a>ShapePlaceStyle 单元格（“Shape Layout”内容）

指定在 "**配置布局**" 对话框 (在 "**设计**" 选项卡上的 "**布局**" 组中, 单击 "**重新布局页面**", 然后单击 "**其他布局选项**") 中排放形状时, 形状在页面上的放置方式。 存储 **VisCellIndices** 中的布局样式和对齐方式值。 
  
|**常量**|**值**|
|:-----|:-----|
|**visLOPlaceBottomToTop** <br/> |4  <br/> |
|**visLOPlaceCircular** <br/> |型  <br/> |
|**visLOPlaceCompactDownLeft** <br/> |日  <br/> |
|**visLOPlaceCompactDownRight** <br/> |步  <br/> |
|**visLOPlaceCompactLeftDown** <br/> |13  <br/> |
|**visLOPlaceCompactLeftUp** <br/> |12  <br/> |
|**visLOPlaceCompactRightDown** <br/> |utf-8  <br/> |
|**visLOPlaceCompactRightUp** <br/> |第  <br/> |
|**visLOPlaceCompactUpLeft** <br/> |11x17  <br/> |
|**visLOPlaceCompactUpRight** <br/> |10  <br/> |
|**visLOPlaceDefault** <br/> |0  <br/> |
|**visLOPlaceHierarchyBottomToTopCenter** <br/> |20  <br/> |
|**visLOPlaceHierarchyBottomToTopLeft** <br/> |合  <br/> |
|**visLOPlaceHierarchyBottomToTopRight** <br/> |不足  <br/> |
|**visLOPlaceHierarchyLeftToRightBottom** <br/> |24  <br/> |
|**visLOPlaceHierarchyLeftToRightMiddle** <br/> |上午  <br/> |
|**visLOPlaceHierarchyLeftToRightTop** <br/> |22  <br/> |
|**visLOPlaceHierarchyRightToLeftBottom** <br/> |27  <br/> |
|**visLOPlaceHierarchyRightToLeftMiddle** <br/> |26  <br/> |
|**visLOPlaceHierarchyRightToLeftTop** <br/> |word  <br/> |
|**visLOPlaceHierarchyTopToBottomCenter** <br/> |×  <br/> |
|**visLOPlaceHierarchyTopToBottomLeft** <br/> |位  <br/> |
|**visLOPlaceHierarchyTopToBottomRight** <br/> |18  <br/> |
|**visLOPlaceLeftToRight** <br/> |双面  <br/> |
|**visLOPlaceParentDefault** <br/> |个  <br/> |
|**visLOPlaceRadial** <br/> |第三章  <br/> |
|**visLOPlaceRightToLeft** <br/> |5  <br/> |
|**visLOPlaceTopToBottom** <br/> |1  <br/> |
   
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称引用 ShapePlaceStyle 单元格，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapePlaceStyle  <br/> |
   
若要从某个程序按索引引用 ShapePlaceStyle 单元格，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOPlaceStyle** <br/> |
   

