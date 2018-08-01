---
title: PlaceFlip 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253251
localization_priority: Normal
ms.assetid: df014b98-cfd5-b6d3-4b8a-b0acb3b94412
description: 确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）时可放置形状在页面上如何翻转和/或旋转。
ms.openlocfilehash: fb16849c7a496a4277133c68453d94d6fd2e67f8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780860"
---
# <a name="placeflip-cell-page-layout-section"></a>PlaceFlip 单元格（“Page Layout”部分）

确定在使用 **“配置布局”** 对话框（在 **“设计”** 选项卡上的 **“布局”** 组中，单击 **“重新布局页面”**，然后单击 **“其他布局选项”**）时可放置形状在页面上如何翻转和/或旋转。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|&amp;H0  <br/> |默认值。不翻转。  <br/> |**visLOFlipDefault** <br/> |
|&amp;H1  <br/> |水平翻转。  <br/> |**visLOFlipX** <br/> |
|&amp;H2  <br/> |垂直翻转。  <br/> |**visLOFlipY** <br/> |
|&amp;H4  <br/> |翻转以 90 度为增量进行。  <br/> |**visLOFlipRotate** <br/> |
|&amp;H8  <br/> |不翻转。  <br/> |**visLOFlipNone** <br/> |
   
## <a name="remarks"></a>注解

PlaceFlip 单元格中的值有助于将可放置形状的方向朝向它连接的下一个可放置形状。该值通常在排放使用静态粘附的绘图时使用。
  
若要为特定形状设置此行为，请使用“Shape Layout”内容中的 ShapePlaceFlip 单元格。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PlaceFlip 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |PlaceFlip  <br/> |
   
若要从某个程序按索引获取对 PlaceFlip 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOPlaceFlip** <br/> |
   

