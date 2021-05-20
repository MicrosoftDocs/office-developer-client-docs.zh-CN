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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429003"
---
# <a name="shdwscalefactor-cell-page-properties-section"></a>ShdwScaleFactor 单元格（“Page Properties”内容）

指定放大或缩小形状阴影的百分比。 
  
## <a name="remarks"></a>备注

每个阴影都有一个阴影的图钉位置，该位置是阴影上对应于形状的图钉的点。 例如，如果形状的固定位于形状的中心，则阴影的固定位置将是阴影的中心点。 将缩放应用于简单阴影时，缩放以阴影的图钉位置为中心;当将缩放应用于倾斜阴影时，缩放将应用于倾斜方向。 
  
 当形状的阴影类型设置为"页面默认值"时， (ShapeShdwType 单元格等于 ** visFSTPageDefault ** ) 。 
  
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
   

