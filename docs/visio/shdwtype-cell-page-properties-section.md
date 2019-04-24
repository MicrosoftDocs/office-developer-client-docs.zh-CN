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
ms.openlocfilehash: f1fc72484d94788ca2798760ca935c89c3e841ad
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342887"
---
# <a name="shdwtype-cell-page-properties-section"></a>ShdwType 单元格（“Page Properties”内容）

指示页面的默认阴影类型。
  
|**Value**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 1  <br/> | 简单  <br/> |**visFSTSimple** <br/> |
| 双面  <br/> | 偏  <br/> |**visFSTOblique** <br/> |
|第三章  <br/> |Inner  <br/> |**visFSTInner** <br/> |
   
## <a name="remarks"></a>注解

 只要 ShapeShdwType 单元格 (页面上的单个形状的阴影类型) 设置为 "页面默认值" (**visFSTPageDefault** ), 此单元格中所述的阴影类型将被使用。 
  
简单阴影类型是指用户界面 (UI) 中的偏移阴影。 简单阴影的效果是将形状的阴影投射到形状背后一段距离的并行面上。 倾斜阴影是指 UI 中的倾斜阴影，其效果是将阴影投射到与形状垂直的面上。 
  
有关预定义的简单阴影类型和倾斜阴影类型的列表，请查看 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）的 **“阴影”** 选项卡上的 **“样式”** 列表。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwType 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShdwType  <br/> |
   
若要从某个程序按索引获取对 ShapeShdwOffsetX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageShdwType** <br/> |
   

