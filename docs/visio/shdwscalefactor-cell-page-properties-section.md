---
title: ShdwScaleFactor 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60083
localization_priority: Normal
ms.assetid: 10979706-6dfe-5241-e862-3f94716d14fa
description: 指定放大或缩小形状阴影的百分比。
ms.openlocfilehash: 99bc48f5332830512e1f5c2f6d93c70b67197c03
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781327"
---
# <a name="shdwscalefactor-cell-page-properties-section"></a>ShdwScaleFactor 单元格（“Page Properties”部分）

指定放大或缩小形状阴影的百分比。 
  
## <a name="remarks"></a>注解

每个阴影具有一个带阴影的 pin 位置，即对应于形状的旋转中心点的阴影上某个点。 例如，如果形状的旋转中心点在形状的中心，则隐藏的 pin 位置就是阴影中心中的点。 阴影方块的 pin 位置中; 将扩展应用于简单阴影，居中显示比例将范围应用于倾斜阴影，显示比例应用倾斜方向。 
  
 形状的阴影类型设置为页面默认值时使用此百分比 (ShapeShdwType 单元格等于 * * visFSTPageDefault * *)。 
  
若要为单个形状设置此行为，请使用“Fill Format”内容中的 ShapeShdwScaleFactor 单元格。
  
此值对应于 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设计”** 箭头）中 **“阴影”** 选项卡上的 **“缩放”** 框中的值。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwScaleFactor 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShdwScaleFactor  <br/> |
   
若要从某个程序按索引获取对 ShdwScaleFactor 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageShdwScaleFactor** <br/> |
   

