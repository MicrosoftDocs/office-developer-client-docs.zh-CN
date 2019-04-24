---
title: ShdwOffsetX 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251373
localization_priority: Normal
ms.assetid: 92ec9b11-f53f-a1c9-832a-6cac08aa5379
description: 确定形状的投影与该形状水平偏移的距离（按页面单位）。
ms.openlocfilehash: fbc7d37fc8ba45f3219af6a4350301102954f23d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338750"
---
# <a name="shdwoffsetx-cell-page-properties-section"></a>ShdwOffsetX 单元格（“Page Properties”内容）

确定形状的投影与该形状水平偏移的距离（按页面单位）。
  
## <a name="remarks"></a>注解

此值在 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）中设置。此值与绘图的缩放比例无关。即使绘图按比例缩放，阴影偏移量也仍保持不变。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwOffsetX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShdwOffsetX  <br/> |
   
若要从某个程序按索引获取对 ShdwOffsetX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageShdwOffsetX** <br/> |
   

