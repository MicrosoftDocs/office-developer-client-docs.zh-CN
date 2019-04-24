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
ms.openlocfilehash: 9175e9a1148779524fdce96ff18eac22fe8dd421
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342880"
---
# <a name="shdwscalefactor-cell-page-properties-section"></a>ShdwScaleFactor 单元格（“Page Properties”内容）

指定放大或缩小形状阴影的百分比。 
  
## <a name="remarks"></a>注解

每个阴影都有一个阴影的固定位置, 这是阴影上与形状的旋转点相对应的点。 例如, 如果形状的旋转中心位于形状的中心, 则阴影的固定位置将成为阴影中心的点。 将 "缩放" 应用于简单阴影时, 放大率以阴影的固定位置为中心。将缩放比例应用到倾斜阴影时, 将以倾斜方向应用放大率。 
  
 当形状的阴影类型设置为 "页面默认值" (ShapeShdwType 单元格等于 * * visFSTPageDefault * *) 时, 将使用此百分比。 
  
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
   

