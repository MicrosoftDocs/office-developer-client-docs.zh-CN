---
title: WalkPreference 单元格（“Glue Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1115
localization_priority: Normal
ms.assetid: 08165195-7e4e-f3ab-fa76-fbcacb0a9c9c
description: 确定一维形状的端点是否移到其所粘附的形状的水平或垂直连接点上（当形状移到不明确的位置上时，使用动态粘附）。默认情况下，一维形状的两个端点都移到水平连接点上。
ms.openlocfilehash: 05f7ded3f7336dc2f8598e8d1e9edc501b511546
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408605"
---
# <a name="walkpreference-cell-glue-info-section"></a>WalkPreference 单元格（“Glue Info”内容）

确定一维形状的端点是否移到其所粘附的形状的水平或垂直连接点上（当形状移到不明确的位置上时，使用动态粘附）。默认情况下，一维形状的两个端点都移到水平连接点上。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 1  <br/> | 一维形状的起点移到垂直连接点，终点移到水平连接点（顶边到侧边连接或底边到侧边连接）。  <br/> |**visWalkPrefBegNS** <br/> |
| 双面  <br/> | 一维形状的起点移到水平连接点，终点移到垂直连接点（侧边到顶边连接或侧边到底边连接）。  <br/> |**visWalkPrefEndNS** <br/> |
   
## <a name="remarks"></a>说明

该单元格对动态连接线没有影响。动态连接线的行为由其排列样式决定。有关绘图页上动态连接线的默认排列样式的信息，请参见 RouteStyle 单元格；有关特定动态连接线的排列样式的信息，请参见 ShapeRouteStyle 单元格。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 WalkPreference 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | WalkPreference  <br/> |
   
要从某个程序按索引获取对 WalkPreference 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowMisc** <br/> |
| 单元格索引：  <br/> |**visWalkPref** <br/> |
   

