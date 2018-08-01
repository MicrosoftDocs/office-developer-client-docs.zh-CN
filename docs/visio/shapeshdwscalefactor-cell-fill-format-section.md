---
title: ShapeShdwScaleFactor 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033175
localization_priority: Normal
ms.assetid: 94ec06c5-8d2f-dd27-1eed-1abaf93daba8
description: 指定形状阴影可放大或缩小的百分比。
ms.openlocfilehash: 0b6392030e7efc8ea36c8d728b99c9b82482840b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781307"
---
# <a name="shapeshdwscalefactor-cell-fill-format-section"></a>ShapeShdwScaleFactor 单元格（“Fill Format”部分）

指定形状阴影可放大或缩小的百分比。
  
## <a name="remarks"></a>注解

每个阴影具有一个带阴影的 pin 位置，即对应于形状的旋转中心点的阴影上某个点。 例如，如果形状的旋转中心点在形状的中心，则隐藏的 pin 位置就是阴影中心中的点。 阴影方块的 pin 位置中; 将扩展应用于简单阴影，居中显示比例将范围应用于倾斜阴影，显示比例应用倾斜方向。 
  
要设置一页中所有形状的这个值，请使用“Page Properties”内容中的 ShdwScaleFactor 单元格。
  
此值对应于 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的 **“缩放”** 设置的值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeShdwScaleFactor 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapeShdwScaleFactor  <br/> |
   
若要从某个程序按索引获取对 ShapeShdwScaleFactor 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowFill** <br/> |
|单元格索引：  <br/> |**visFillShdwScaleFactor** <br/> |
   

