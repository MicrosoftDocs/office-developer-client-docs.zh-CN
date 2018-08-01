---
title: ShapeShdwType 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033173
localization_priority: Normal
ms.assetid: 1461148d-90a9-6f7c-1b28-9310ffaf0e3b
description: 指定形状的阴影类型。
ms.openlocfilehash: b96ad4a877d72bf4457ec3cf038a29a2b414e0f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781287"
---
# <a name="shapeshdwtype-cell-fill-format-section"></a>ShapeShdwType 单元格（“Fill Format”部分）

指定形状的阴影类型。 
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |使用页面默认值（默认值）  <br/> |**visFSTPageDefault** <br/> |
|1  <br/> |简单  <br/> |**visFSTSimple** <br/> |
|2  <br/> |倾斜  <br/> |**visFSTOblique** <br/> |
   
## <a name="remarks"></a>说明

使用此单元格应用形状阴影的不同页面默认值 （在属性页部分的 ShdwType 单元格定义页面默认阴影类型）。
  
用户界面 (UI) 中的偏移阴影介绍简单阴影类型。 简单阴影效果的形状的阴影投射到的并行面上形状后面。 倾斜阴影倾斜阴影在 UI 中所述，并为被强制转换到平面上垂直到形状的阴影效果。 
  
有关预定义的简单阴影和倾斜阴影类型的列表，请查看 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的 **“样式”** 框。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeShdwType 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapeShdwType  <br/> |
   
若要从某个程序按索引获取对 ShapeShdwType 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowFill** <br/> |
|单元格索引：  <br/> |**visFillShdwType** <br/> |
   

