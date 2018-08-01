---
title: ShapePlaceFlip 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253247
localization_priority: Normal
ms.assetid: 40008507-d9e4-9c0e-603f-d5e6da73a94b
description: 确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）排放形状时，可放置形状在页面上如何翻转、旋转或同时翻转和旋转。
ms.openlocfilehash: 76941b9c50e6f2c68ea9abf54e81dcd18be13a70
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781271"
---
# <a name="shapeplaceflip-cell-shape-layout-section"></a>ShapePlaceFlip 单元格（“Shape Layout”部分）

确定在使用 **“配置布局”** 对话框（在 **“设计”** 选项卡上的 **“布局”** 组中，单击 **“重新布局页面”**，然后单击 **“其他布局选项”**）排放形状时，可放置形状在页面上如何翻转、旋转或同时翻转和旋转。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |使用页默认值。  <br/> |**visLOFlipDefault** <br/> |
|1  <br/> |水平翻转。  <br/> |**visLOFlipX** <br/> |
|2  <br/> |垂直翻转。  <br/> |**visLOFlipY** <br/> |
|4  <br/> |以 90 度为增量在 0 到 270 度之间翻转。  <br/> |**visLOFlipRotate** <br/> |
|8  <br/> |不翻转。  <br/> |**visLOFlipNone** <br/> |
   
## <a name="remarks"></a>注解

ShapePlaceFlip 单元格中的值有助于将可放置形状的方向朝向它连接的下一个可放置形状。
  
若要在绘图页上设置此行为*所有*形状，请用页面布局部分中的 PlaceFlip 单元格。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapePlaceFlip 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapePlaceFlip  <br/> |
   
若要从某个程序按索引获取对 ShapePlaceFlip 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOPlaceFlip** <br/> |
   

