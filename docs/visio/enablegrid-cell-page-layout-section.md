---
title: EnableGrid 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251642
localization_priority: Normal
ms.assetid: bfea4ef4-1b30-eb22-215d-3b9b73098da9
description: 确定在 "配置布局" 对话框中配置布局时, 应用程序是否基于内部不可见的页面网格排放形状。 (在 "设计" 选项卡上的 "布局" 组中, 单击 "重新布局页面", 然后单击 "其他布局选项"。)
ms.openlocfilehash: 11299ca7c9b0ea050542baf97e2cab3a27fa52ba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424439"
---
# <a name="enablegrid-cell-page-layout-section"></a>EnableGrid 单元格（“Page Layout”内容）

确定在 **“配置布局”** 对话框中配置布局时应用程序是否根据内部不可见的页面网格排放形状。（在 **“设计”** 选项卡上的 **“布局”** 组中，单击 **“重新布局页面”**，然后单击 **“其他布局选项”**。）
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |使用内部页网格。  <br/> |
|FALSE  <br/> |不使用内部页网格。  <br/> |
   
## <a name="remarks"></a>说明

可以使用 **“布局与排列间距”** 对话框中的 **“形状间的距离”** 和 **“平均形状大小”** 值创建此页面网格。（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，单击 **“布局与排列”**，然后单击 **“间距”**。） 
  
启用此功能后，应用程序会将每个可放置形状的中心点与内部页网格上的块的中心对齐。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 EnableGrid 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |EnableGrid  <br/> |
   
若要从某个程序按索引获取对 EnableGrid 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOEnableGrid** <br/> |
   

