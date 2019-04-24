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
ms.openlocfilehash: 607881e4a520f1376562394c6e40ab5d2508906d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342859"
---
# <a name="shapeshdwtype-cell-fill-format-section"></a>ShapeShdwType 单元格（“Fill Format”内容）

指定形状的阴影类型。 
  
|**Value**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |使用页面默认值（默认值）  <br/> |**visFSTPageDefault** <br/> |
|1  <br/> |简单  <br/> |**visFSTSimple** <br/> |
|双面  <br/> |偏  <br/> |**visFSTOblique** <br/> |
   
## <a name="remarks"></a>注解

使用此单元格应用与页面默认值不同的形状阴影 (页面默认阴影类型是在 "页面属性" 部分的 "ShdwType" 单元格中定义)。
  
简单阴影类型是指用户界面 (UI) 中的偏移阴影。 简单阴影的效果是将形状的阴影投射到形状背后一段距离的并行面上。 倾斜阴影是指 UI 中的倾斜阴影，其效果是将阴影投射到与形状垂直的面上。 
  
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
   

