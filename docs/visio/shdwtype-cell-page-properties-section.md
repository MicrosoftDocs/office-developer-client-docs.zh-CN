---
title: ShdwType 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60084
localization_priority: Normal
ms.assetid: 551166d0-3aaa-0fd7-e742-cf3450ba90ed
description: 指示页面的默认阴影类型。
ms.openlocfilehash: 1fc5c31a723d5d409110d94ff543a45dadabf264
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781336"
---
# <a name="shdwtype-cell-page-properties-section"></a>ShdwType 单元格（“Page Properties”内容）

指示页面的默认阴影类型。
  
|**值**|**说明**|**自动化常量**|
|:-----|:-----|:-----|
| 1  <br/> | 简单  <br/> |**visFSTSimple** <br/> |
| 2  <br/> | 倾斜  <br/> |**visFSTOblique** <br/> |
|3  <br/> |内部  <br/> |**visFSTInner** <br/> |
   
## <a name="remarks"></a>备注

 ShapeShdwType 单元格 （页上的单个形状的阴影类型） 设置为页面默认值 (**visFSTPageDefault** ) 时使用此单元格中描述的阴影类型。 
  
用户界面 (UI) 中的偏移阴影介绍简单阴影类型。 简单阴影效果的形状的阴影投射到位于其背后一些距离并行平面。 倾斜阴影倾斜阴影在 UI 中所述，并为被强制转换到平面上垂直到形状的阴影效果。 
  
预定义的简单和倾斜阴影类型的列表，请参阅**样式**列表**页面设置**对话框的**阴影**选项卡 （**设计**选项卡中，单击**页面设置**箭头）。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ShdwType 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShdwType  <br/> |
   
若要从某个程序按索引获取对 ShapeShdwOffsetX 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageShdwType** <br/> |
   

